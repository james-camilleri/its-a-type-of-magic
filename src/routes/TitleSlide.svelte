<script lang="ts">
  import { onMount } from 'svelte'

  export let title = "it's a\n>kind<type of\nmagic"
  export let subtitle = ''

  let element: HTMLElement
  let displayTitle = ''
  let displaySubtitle = false
  let animated = false

  function random(min: number, max: number) {
    return Math.random() * (max - min) + min
  }

  const DELAY = 200

  onMount(() => {
    let deleteTill = 0
    let offset = 0

    const observer = new MutationObserver((mutations) => {
      mutations.forEach((mutation) => {
        if (
          mutation.type === 'attributes' &&
          mutation.attributeName === 'class' &&
          element.classList.contains('present') &&
          !animated
        ) {
          title.split('').forEach((letter, i) => {
            if (letter === '>') {
              deleteTill = i
              return
            }

            if (letter === '<') {
              const charsToDelete = i - deleteTill
              offset = charsToDelete

              for (let j = 0; j < charsToDelete - 1; j++) {
                setTimeout(() => {
                  displayTitle = displayTitle.slice(0, -1)
                }, DELAY + (100 * (i + j) - 1) + random(80, 120))
              }

              return
            }

            setTimeout(() => {
              displayTitle += letter
            }, DELAY + (100 * (i + offset) - 1) + random(80, 120))
          })

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

<section bind:this={element}>
  {#if title}
    <h1>{displayTitle}</h1>
  {/if}
  {#if displaySubtitle}
    <p class:subtitle-only={!title}>{subtitle}</p>
  {/if}
</section>

<style lang="scss">
  h1 {
    white-space: pre;
  }

  p {
    margin-top: var(--lg);
  }
</style>
