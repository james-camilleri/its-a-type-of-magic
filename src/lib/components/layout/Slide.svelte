<script lang="ts">
  import { onMount } from 'svelte'
  import Caption from './Caption.svelte'

  export let title = ''
  export let subtitle = ''
  export let large = false
  export let small = false
  export let contain = false
  export let animate = false
  export let loop = false
  export let image = ''
  export let video = ''
  export let iframe = ''
  export let caption: string | string[] | undefined = undefined

  let element: HTMLElement
  let displayTitle = ''
  let displaySubtitle = false
  let animated = false

  const dataAttributes = image
    ? {
        'data-background-image': image,
        'data-background-size': contain ? 'contain' : 'cover',
      }
    : video
    ? {
        'data-background-video': video,
        'data-background-video-loop': loop,
      }
    : iframe
    ? {
        'data-background-iframe': iframe,
        'data-background-interactive': true,
      }
    : {
        'data-auto-animate': animate || undefined,
      }

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

<section bind:this={element} {...dataAttributes} class:small>
  {#if title}
    <h1 class:large>{displayTitle}</h1>
  {/if}
  {#if displaySubtitle}
    <p class:subtitle-only={!title}>{subtitle}</p>
  {/if}

  <Caption {caption} />
</section>

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

  .underscore {
    color: var(--primary);
  }

  .subtitle-only {
    font-size: var(--xl);
  }
</style>
