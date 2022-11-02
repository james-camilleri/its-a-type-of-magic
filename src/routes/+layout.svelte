<script lang="ts">
  import 'reveal.js/dist/reveal.css'
  import 'reveal.js/dist/theme/white.css'
  import '../styles/global.scss'
  import { browser } from '$app/environment'

  async function initialiseReveal() {
    const { default: Reveal } = await import('reveal.js')
    const deck = new Reveal()
    deck.initialize({
      center: false,
      preloadIframes: true,
      controlsTutorial: true,
      hash: true,
      respondToHashChanges: true,
      autoPlayMedia: true,
    })
  }

  if (browser) {
    initialiseReveal()
  }
</script>

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
