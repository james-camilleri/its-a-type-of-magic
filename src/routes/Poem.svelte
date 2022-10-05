<script lang="ts">
  import Grid from '$lib/components/layout/Grid.svelte'
  import { onMount } from 'svelte'

  export let conversation: { question: string; answer: string }[] = []
  export let seeds: string[] = []
  export let poem: string
  let displayPoem = ''

  let element: HTMLElement
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
          poem.split('').map((letter, i) =>
            setTimeout(() => {
              displayPoem += letter
            }, DELAY + (50 * i - 1) + random(20, 50)),
          )

          animated = true
        }
      })
    })

    observer.observe(element, { attributes: true })
  })
</script>

<section bind:this={element}>
  <Grid columns={[2, 3]}>
    <div>
      {#each conversation as { question, answer }}
        <div class="q-and-a">
          <div class="question">{question}</div>
          <div>{answer}</div>
        </div>
      {/each}
    </div>
    <div class="poem-and-seeds">
      <div class="seeds">
        ({seeds.join(', ')})
      </div>
      <div class="poem">
        {displayPoem}
      </div>
    </div>
  </Grid>
</section>

<style lang="scss">
  .q-and-a {
    margin-bottom: var(--sm);
    font-size: 1rem;
    font-weight: 300;
    text-align: left;

    .question {
      font-weight: 500;
      &::after {
        color: var(--primary);
        content: '_';
      }
    }
  }

  .poem-and-seeds {
    text-align: left;

    .seeds {
      margin-bottom: var(--md);
      font-weight: 300;
    }

    .poem {
      font-size: 0.8em;
      white-space: pre-line;
      &::after {
        color: var(--primary);
        content: '_';
      }
    }
  }
</style>
