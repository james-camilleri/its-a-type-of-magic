<script lang="ts">
  import { onMount } from 'svelte'

  export let title = ''
  export let subtitle = ''
  export let large = false
  export let small = false
  export let animate = false
  export let loop = false
  export let image = ''
  export let video = ''

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
  <section bind:this={element} data-background-image={image} />
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

<style>
  .large {
    font-size: calc(var(--xxl) * var(--ratio));
  }

  .small :global(:not(h1, h2, h3)) {
    font-size: calc(var(--r-main-font-size) * 0.66);
  }

  p {
    margin-top: var(--lg);
  }

  .subtitle-only {
    font-size: var(--xl);
  }
</style>
