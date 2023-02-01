<script lang="ts">
  import 'reveal.js/dist/reveal.css'
  import 'reveal.js/dist/theme/white.css'
  // import 'reveal.js/plugin/highlight/monokai.css'
  import '../styles/syntax-highlight.css'
  import '../styles/global.scss'
  import { browser } from '$app/environment'

  import Navigation from '$lib/components/global/Navigation.svelte'

  let time = 0
  let interval: number

  function keyListener(e: KeyboardEvent) {
    if (e.key === 't') {
      interval ? stopTimer() : startTimer()
    }
  }

  function startTimer() {
    interval = setInterval(() => {
      time++
    }, 1000)
  }

  function stopTimer() {
    clearInterval(interval)
    interval = 0
  }

  function pad(number: number) {
    const string = number.toString()
    return string.length === 1 ? `0${string}` : string
  }

  async function initialiseReveal() {
    const { default: Reveal } = await import('reveal.js')
    const { default: RevealHighlight } = await import(
      'reveal.js/plugin/highlight/highlight.js'
    )

    const deck = new Reveal({
      plugins: [RevealHighlight],
    })

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
    'interaction-design': 5,
    inspiration: 13,
    'conceptual-approach': 20,
    construction: 23,
    performances: 38,
    'next-steps': 66,
    bibliography: 71,
  }
</script>

<svelte:window on:keydown={keyListener} />
<Navigation items={navItems} />
<div class="reveal">
  <div class="slides">
    <slot />
  </div>
</div>
<div class="timer">
  {pad(Math.floor(time / 60))}<span>:</span>{pad(time % 60)}
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

  .timer {
    position: fixed;
    bottom: 2rem;
    left: 2rem;
    z-index: 1;
    width: 3rem;
    padding: 0.2rem 0.2rem 0.1rem;
    text-align: center;
    background: var(--r-background-color);
    border-radius: 1px;
    opacity: 0.5;

    span {
      position: relative;
      top: -0.1em;
      padding: 0 0.05rem;
      color: var(--primary);
    }
  }
</style>
