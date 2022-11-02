<script lang="ts">
  import { page } from '$app/stores'

  export let items: Record<string, number>

  let navOpen = false
  // There's no way to use bind:this conditionally as of 20/02/2022, so
  // we need to store all refs and just use the first one for focus capture.
  let navItemRefs: HTMLElement[] = []
  let menuButtonRef: null | HTMLElement = null

  function close() {
    navOpen = false
  }

  function toggle() {
    navOpen = !navOpen
  }

  function handleKeydown(e: KeyboardEvent) {
    // Only handle closing and focus capture on the mobile menu.
    if (!navOpen) return

    if (e.key === 'Escape') {
      close()
    }

    // Capture focus when tabbing.
    if (e.key === 'Tab') {
      if (menuButtonRef === document.activeElement && !e.shiftKey) {
        e.preventDefault()
        navItemRefs[0].focus()
        return
      }

      if (navItemRefs[0] === document.activeElement && e.shiftKey) {
        e.preventDefault()
        menuButtonRef?.focus()
        console.log('document.activeElement', document.activeElement)
        return
      }
    }
  }
</script>

<svelte:window on:keydown={handleKeydown} />
<div>
  <nav class:open={navOpen}>
    <ul>
      {#each Object.entries(items) as [text, slideNumber]}
        <li>
          <a
            class="nav-item"
            href={$page.url.origin + `#/${slideNumber}`}
            on:click={close}
          >
            {text.replaceAll('-', ' ')}
          </a>
        </li>
      {/each}
    </ul>
  </nav>

  <button
    aria-controls="navigation"
    class="menu-button"
    type="button"
    on:click={toggle}
    bind:this={menuButtonRef}
  >
    <div class="hamburger" class:active={navOpen}>
      <span class="screen-reader-only">Open/close navigation</span>
    </div>
  </button>
</div>

<style lang="scss">
  @use '../../../styles/breakpoints';

  nav {
    // Full-screen mobile navigation.
    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    left: 80vw;
    z-index: 5;

    display: flex;
    flex-direction: column;
    overflow: auto;

    font-size: 1.3em;
    background: var(--dark);
    opacity: 0.9;

    transition: opacity var(--transition-fast) ease-in-out,
      transform 0s ease-in-out var(--transition-fast);

    &:not(.open) {
      opacity: 0;
      transform: translateY(100%);
    }
  }

  ul {
    display: flex;
    flex-direction: column;
    justify-content: center;
    margin: auto 0;
  }

  .nav-item {
    --hover-background: var(--primary);
    --hover-colour: var(--background);
    --active-background: var(--secondary);
    --active-colour: var(--foreground);

    color: var(--light);
    text-align: center;
    text-decoration: none;
    overflow-wrap: normal;

    transition: color var(--transition-fast) ease-in-out,
      background-color var(--transition-fast) ease-in-out;

    &:hover,
    &:focus {
      outline: none;
    }
  }

  a {
    display: block;
    padding: var(--md);

    &:hover,
    &:focus {
      color: var(--hover-colour);
      background: var(--hover-background);
    }
  }

  a.active {
    color: var(--foreground);
    background: var(--secondary);
  }

  .menu-button {
    --size: 4rem;
    --padding: var(--md);
    --button-colour: var(--primary);
    --icon-colour: var(--secondary);

    // Used when tabbing to the menu button, for accessibility.
    --focus-ring-colour: var(--secondary);

    // You can probably leave these alone.
    --bar-width: calc(var(--size) - (var(--padding) * 2));
    --bar-height: calc(var(--bar-width) / 5);

    position: fixed;
    top: var(--lg);
    right: var(--lg);
    z-index: 10;
    width: var(--size);
    height: var(--size);
    padding: var(--padding);
    cursor: pointer;

    background: none;
    border: 0;
    border-radius: 100%;
    transition: transform var(--transition-fast) ease-in-out;

    &:hover,
    &:focus {
      transform: scale(1.2);
    }

    // Add focus ring for rare cases when button is tabbed into.
    &:focus {
      outline: 5px solid var(--focus-ring-colour);
    }

    &:focus:not(:focus-visible) {
      outline: none;
    }

    // Scale button back down after it's cliccked on.
    &:focus:not(:focus-visible):not(:hover) {
      transform: scale(1);
    }
  }

  .hamburger {
    top: 50%;
    margin-top: calc(var(--bar-height) / -2);

    transition-timing-function: cubic-bezier(0.55, 0.055, 0.675, 0.19);
    transition-duration: 0.22s;

    &,
    &::before,
    &::after {
      position: absolute;
      width: var(--bar-width);
      height: var(--bar-height);
      background-color: var(--icon-colour);
      border-radius: var(--bar-height);
      transition: transform var(--transition-fast) ease;
    }

    &::before,
    &::after {
      display: block;
      content: '';
    }

    &::before {
      top: calc(var(--bar-height) * -1.5);
      transition: top 0.1s 0.25s ease-in, opacity 0.1s ease-in;
    }

    &::after {
      bottom: calc(var(--bar-height) * -1.5);
      transition: bottom 0.1s 0.25s ease-in,
        transform 0.22s cubic-bezier(0.55, 0.055, 0.675, 0.19);
    }
  }

  // Animations based on "Hamburgers" by Jonathan Suh @jonsuh
  // @link https://github.com/jonsuh/hamburgers
  .hamburger.active {
    transition-delay: 0.12s;
    transition-timing-function: cubic-bezier(0.215, 0.61, 0.355, 1);
    transform: rotate(225deg);

    &::before {
      top: 0;
      opacity: 0;
      transition: top 0.1s ease-out, opacity 0.1s 0.12s ease-out;
    }

    &::after {
      bottom: 0;
      transition: bottom 0.1s ease-out,
        transform 0.22s 0.12s cubic-bezier(0.215, 0.61, 0.355, 1);
      transform: rotate(-90deg);
    }
  }
</style>
