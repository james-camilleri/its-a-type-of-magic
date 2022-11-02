<script>
  import Grid from '$lib/components/layout/Grid.svelte'
  import CoverImage from './CoverImage.svelte'
  import VennDiagram from '$assets/images/venn-diagram.png'
</script>

<section>
  <Grid columns={2} gap="var(--xl)">
    <p>
      The role of the artist, the audience, and the artwork during an
      interactive performance – specifically, a performance which takes place on
      stage – and the idea that both the performer and the audience are the
      creators of an interactive performance has contributed to the
      conceptualization and development of Typo.
    </p>
    <CoverImage
      src={VennDiagram}
      alt="Venn diagram showing intersection of art, artist and audience"
    />
  </Grid>
</section>

<style>
  p {
    font-size: 1.3rem;
    font-weight: 300;
    text-align: left;
  }
</style>
