<script>
  let name = "Stuart <button>Minnion</button>";
  import src from "./assets/giphy.gif";
  import Nested from "./lib/Nested.svelte";
</script>

<h1>Hello {@html name.toUpperCase()}</h1>
<img {src} alt="{name} alert" />
<Nested />

<style>
  h1 {
    color: lightblue;
  }
</style>
