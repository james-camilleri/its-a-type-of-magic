<script>
  export let src = ''
  export let alt = ''
</script>

<img {src} {alt} />

<style>
  img {
    width: 100%;
    max-width: 100%;
    height: 100%;
    max-height: 100%;
    margin: 0;
    object-fit: cover;
  }
</style>
