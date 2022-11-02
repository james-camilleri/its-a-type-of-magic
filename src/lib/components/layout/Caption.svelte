<script lang="ts">
  export let caption: string | string[] | undefined

  const [main, sub, ...description] = caption
    ? Array.isArray(caption)
      ? caption
      : [caption]
    : []
</script>

{#if caption && caption.length > 0}
  <div class="caption">
    <span class="main">{main}<span class="underscore">_</span></span>

    {#if sub}
      <span class="sub">{sub}</span>
    {/if}

    {#if description}
      {#each description as text}
        <p>{text}</p>
      {/each}
    {/if}
  </div>
{/if}

<style>
  .caption {
    position: fixed;
    right: -250px;
    bottom: 3rem;
    display: flex;
    flex-direction: column;
    max-width: 40vw;
    padding: 1rem 6rem 1rem 1rem;
    font-size: 1.2rem;
    font-weight: 300;
    text-align: right;
    background: rgb(255 255 255 / 90%);
  }

  .main {
    font-weight: 400;
    text-transform: lowercase;
  }

  p {
    margin: 0.5em 0 0;
    font-size: 0.8em;
  }

  .underscore {
    color: var(--primary);
  }
</style>
