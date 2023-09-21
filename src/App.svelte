<script>
  let name = "Stuart";
  import src from "./assets/giphy.gif";
  import Nested from "./lib/Nested.svelte";
</script>

<h1>Hello {name.toUpperCase()}</h1>
<img {src} alt="{name} alert" />
<Nested />

<style>
  h1 {
    color: lightblue;
  }
</style>
