<script>
  import Interaction1 from '$assets/images/interaction-1.jpg'
  import Interaction2 from '$assets/images/interaction-2.jpg'
  import Interaction3 from '$assets/images/interaction-3.jpg'
  import Interaction4 from '$assets/images/interaction-4.jpg'
  import Interaction5 from '$assets/images/interaction-5.jpg'
  import Interaction6 from '$assets/images/interaction-6.jpg'
  import Grid from '$lib/components/layout/Grid.svelte'
  import CoverImage from './CoverImage.svelte'
</script>

<section>
  <Grid columns={[2, 1]}>
    <Grid columns={2} gap="var(--sm)">
      <div class="wrapper">
        <CoverImage src={Interaction1} alt="interaction-1" /><span>1</span>
      </div>
      <div class="wrapper">
        <CoverImage src={Interaction2} alt="interaction-2" /><span>2</span>
      </div>
      <div class="wrapper">
        <CoverImage src={Interaction3} alt="interaction-3" /><span>3</span>
      </div>
      <div class="wrapper">
        <CoverImage src={Interaction4} alt="interaction-4" /><span>4</span>
      </div>
      <div class="wrapper">
        <CoverImage src={Interaction5} alt="interaction-5" /><span>5</span>
      </div>
      <div class="wrapper">
        <CoverImage src={Interaction6} alt="interaction-6" /><span>6</span>
      </div>
    </Grid>
    <ol>
      <li>Motion sensor activates as audience walks by.</li>
      <li>Typo greets the audience and asks a question.</li>
      <li>Audience holds the button to activate microphone.</li>
      <li>The answer to the questionis spoken into the microphone.</li>
      <li>After three questions have been answered, Typo generates a poem.</li>
      <li>
        The audience can take their personal poem with them by cutting it off
        the roll of paper.
      </li>
    </ol>
  </Grid>
</section>

<style>
  .wrapper {
    position: relative;
  }

  span {
    position: absolute;
    right: 0.5em;
    bottom: 0.5em;
    padding: var(--xs) var(--sm);
    font-size: var(--sm);
    color: var(--light);
    background: var(--dark);
  }

  ol {
    font-size: 1rem;
    font-weight: 300;
    list-style: none;
    counter-reset: counter;
  }

  ol li {
    counter-increment: counter;
  }

  ol li::before {
    font-weight: 400;
    content: counter(counter) '. ';
  }

  li:not(:last-child) {
    margin-bottom: 1rem;
  }
</style>
