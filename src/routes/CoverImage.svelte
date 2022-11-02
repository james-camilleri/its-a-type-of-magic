<script>
  export let src = ''
  export let alt = ''
</script>

<img {src} {alt} />

<style>
  img {
    max-width: 100%;
    max-height: 100%;
    margin: 0;
    object-fit: cover;
  }
</style>
