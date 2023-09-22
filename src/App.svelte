<script>
  let name = "Stuart <button>Minnion</button>";
  import src from "./assets/giphy.gif";
  import Nested from "./lib/Nested.svelte";
  let counter = 0;

  function increment() {
    counter += 1;
  }
  $: doubled = counter * 2;
</script>

<!-- <h1>Hello {@html name.toUpperCase()}</h1>
<img {src} alt="{name} alert" />
<Nested />
<button on:click={increment}>
  Increase my counter {counter}
</button> -->
<h1>{counter}</h1>
<button on:click={() => (counter += 1)}>Increment</button>
<button on:click={() => (counter -= 1)}>Decrement</button>
<h1>{doubled} Double</h1>

<style>
  h1 {
    color: lightblue;
  }
</style>
