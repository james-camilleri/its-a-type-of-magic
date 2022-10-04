<script lang="ts">
  import { onMount } from 'svelte'

  export let title = ''
  export let subtitle = ''
  export let large = false
  export let small = false
  export let contain = false
  export let animate = false
  export let loop = false
  export let image = ''
  export let video = ''
  export let caption: string | string[] | undefined = undefined

  let element: HTMLElement
  let displayTitle = ''
  let displaySubtitle = false
  let animated = false

  function random(min: number, max: number) {
    return Math.random() * (max - min) + min
  }

  const DELAY = 200

  onMount(() => {
    const observer = new MutationObserver((mutations) => {
      mutations.forEach((mutation) => {
        if (
          mutation.type === 'attributes' &&
          mutation.attributeName === 'class' &&
          element.classList.contains('present') &&
          !animated
        ) {
          title.split('').map((letter, i) =>
            setTimeout(() => {
              displayTitle += letter
            }, DELAY + (100 * i - 1) + random(80, 120)),
          )

          if (subtitle) {
            setTimeout(() => {
              displaySubtitle = true
            }, DELAY + (title.split('').length + 1) * 120)
          }

          animated = true
        }
      })
    })

    observer.observe(element, { attributes: true })
  })
</script>

{#if image}
  <section
    bind:this={element}
    data-background-image={image}
    data-background-size={contain ? 'contain' : 'cover'}
  >
    {#if caption && caption.length > 0}
      <div class="caption">
        <span
          >{typeof caption === 'string' ? caption : caption[0]}<span
            class="underscore">_</span
          ></span
        >
        {#if Array.isArray(caption)}
          {#each caption.slice(1) as text}
            <span>{text}</span>
          {/each}
        {/if}
      </div>
    {/if}
  </section>
{:else if video}
  <section
    bind:this={element}
    data-background-video={video}
    data-background-video-loop={loop}
  />
{:else}
  <section
    bind:this={element}
    class:small
    data-auto-animate={animate || undefined}
  >
    {#if title}
      <h1 class:large>{displayTitle}</h1>
    {/if}
    {#if displaySubtitle}
      <p class:subtitle-only={!title}>{subtitle}</p>
    {/if}
    <slot />
  </section>
{/if}

<style lang="scss">
  .large {
    font-size: calc(var(--xxl) * var(--ratio));
  }

  .small :global(:not(h1, h2, h3)) {
    font-size: calc(var(--r-main-font-size) * 0.66);
  }

  p {
    margin-top: var(--lg);
  }

  .caption {
    position: fixed;
    right: -250px;
    bottom: 3rem;
    display: flex;
    flex-direction: column;
    padding: 1rem 3rem 1rem 1rem;
    font-size: 1.2rem;
    font-weight: 300;
    text-align: right;
    background: rgb(255 255 255 / 90%);

    > span:first-child {
      font-weight: 400;
    }
  }

  .underscore {
    color: var(--primary);
  }

  .subtitle-only {
    font-size: var(--xl);
  }
</style>
