<script lang="ts">
  import 'reveal.js/dist/reveal.css'
  import 'reveal.js/dist/theme/white.css'
  import '../styles/global.scss'
  import { browser } from '$app/environment'

  import Navigation from '$lib/components/global/Navigation.svelte'

  async function initialiseReveal() {
    const { default: Reveal } = await import('reveal.js')
    const deck = new Reveal()
    deck.initialize({
      center: false,
      preloadIframes: true,
      controlsTutorial: true,
      hash: true,
      hashOneBasedIndex: true,
      respondToHashChanges: true,
      autoPlayMedia: true,
    })
  }

  if (browser) {
    initialiseReveal()
  }

  const navItems = {
    introduction: 1,
    inspiration: 1,
    concept: 1,
    thesis: 1,
    'interaction-design': 1,
    construction: 1,
    performances: 1,
    'next-steps': 1,
    bibliography: 1,
    appendix: 1,
  }
</script>

<Navigation items={navItems} />
<div class="reveal">
  <div class="slides">
    <slot />
  </div>
</div>

<style lang="scss">
  .reveal {
    :global(h2) {
      font-weight: 300;
    }

    :global(section) {
      //  Forgive me.
      display: flex !important;
      flex-direction: column !important;
      justify-content: center !important;
      height: 100%;
    }
  }
</style>
