<script>
  let name = "Stuart <button>Minnion</button>";
  import src from "./assets/giphy.gif";
  import Nested from "./lib/Nested.svelte";
  import PackageInfo from "./lib/PackageInfo.svelte";

  let counter = 0;

  function increment() {
    counter += 1;
  }
  $: doubled = counter * 2;

  $: {
    console.log(counter);
    if (counter > 10) alert("BIG BOY");
  }

  let todos = ["eat", "sleep", "go to office", "work", "repeat"];

  $: {
    console.log(todos);
  }

  function addTodo() {
    // todos.push("drink");
    // todos = todos;
    todos = [...todos, "code"];
  }

  const pkg = {
    name: "svelte",
    speed: "blazing",
    version: 4,
    website: "https://svelte.dev",
  };

  let user = null;
</script>

<!-- <h1>Hello {@html name.toUpperCase()}</h1>
<img {src} alt="{name} alert" />
<Nested />
<button on:click={increment}>
  Increase my counter {counter}
</button>
<h1>{counter}</h1>
<button on:click={() => (counter += 1)}>Increment</button>
<button on:click={() => (counter -= 1)}>Decrement</button>
<h1>{doubled} Double</h1>

<button on:click={addTodo}>Add a new Todo</button> -->

<h1>So this is coming from APP</h1>
<!-- <Nested x={0} y={0} /> -->
<Nested />

<PackageInfo
  name={pkg.name}
  speed={pkg.speed}
  version={pkg.version}
  website={pkg.website}
/>

<button on:click={() => (user = !user)}>Sign In</button>

{#if !user}
  <h1>Please sign in</h1>
{:else}
  <h1>Welcome {@html name} 🚨</h1>
{/if}

<style>
  h1 {
    color: lightblue;
  }
</style>
