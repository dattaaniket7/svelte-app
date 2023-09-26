<script>
  // let name = "Stuart <button>Minnion</button>";
  // import src from "./assets/giphy.gif";
  // import Nested from "./lib/Nested.svelte";
  // import PackageInfo from "./lib/PackageInfo.svelte";
  // import { getRandomNumber } from "./lib/utils";
  import Inner from "./lib/Inner.svelte";
  import Outer from "./lib/Outer.svelte";
  import BigRedButton from "./lib/BigRedButton.svelte";
  import horn from "./assets/horn.mp3";

  // let counter = 0;

  // function increment() {
  //   counter += 1;
  // }
  // $: doubled = counter * 2;

  // $: {
  //   console.log(counter);
  //   if (counter > 10) alert("BIG BOY");
  // }

  // let todos = ["eat", "sleep", "go to office", "work", "repeat"];

  // $: {
  //   console.log(todos);
  // }

  // function addTodo() {
  //   todos.push("drink");
  //   todos = todos;
  //   todos = [...todos, "code"];
  // }

  // const pkg = {
  //   name: "svelte",
  //   speed: "blazing",
  //   version: 4,
  //   website: "https://svelte.dev",
  // };

  // let user = null;

  // let count = 0;

  // function increment() {
  //   count += 1;
  // }

  // const colors = [
  //   "red",
  //   "orange",
  //   "yellow",
  //   "green",
  //   "blue",
  //   "indigo",
  //   "violet",
  // ];
  // let selected = colors[0];

  // const users = [
  //   { name: "oldMonk", id: crypto.randomUUID() },
  //   { name: "xpert", id: crypto.randomUUID() },
  //   { name: "kartos", id: crypto.randomUUID() },
  //   { name: "ed", id: crypto.randomUUID() },
  // ];

  // let promise = getRandomNumber();

  // function handleClick() {
  //   promise = getRandomNumber();
  // }

  // let m = { x: 0, y: 0 };
  // function handleMove(event) {
  //   m.x = event.clientX;
  //   m.y = event.clientY;
  // }

  function handleMessage(event) {
    alert(event.detail.text);
  }

  const audio = new Audio();
  audio.src = horn;

  function handleClick() {
    audio.play();
  }

  let name = "world";
</script>

<!-- <h1>Hello {@html name.toUpperCase()}</h1> -->
<!-- <img {src} alt="{name} alert" /> -->
<!-- <Nested /> -->

<!-- <button on:click={increment}>
  Increase my counter {counter}
</button>
<h1>{counter}</h1>
<button on:click={() => (counter += 1)}>Increment</button>
<button on:click={() => (counter -= 1)}>Decrement</button>
<h1>{doubled} Double</h1> -->

<!-- <button on:click={addTodo}>Add a new Todo</button> -->

<!-- <h1>So this is coming from APP</h1> -->
<!-- <Nested x={0} y={0} /> -->
<!-- <Nested /> -->

<!-- <PackageInfo
  name={pkg.name}
  speed={pkg.speed}
  version={pkg.version}
  website={pkg.website}
/> -->

<!-- <button on:click={() => (user = !user)}>Sign In</button>

{#if !user}
  <h1>Please sign in</h1>
{:else}
  <h1>Welcome {@html name} 🚨</h1>
{/if} -->

<!-- <button on:click={increment}>
  Clicked {count}
  {count === 1 ? "time" : "times"}
</button> -->

<!-- {#if count > 10}
  <p>{count} is greater than 10</p>
{:else if count < 5}
  <p>{count} is less than 5</p>
{:else}
  <p>{count} is between 0 and 10</p>
{/if} -->

<!-- <h1 style="color: {selected};">Pick a color</h1> -->

<!-- <div>
  <button
    aria-current={selected === "red"}
    aria-label="red"
    style="background: red;"
    on:click={() => (selected = "red")}
  />
  <button
    aria-current={selected === "orange"}
    aria-label="orange"
    style="background: orange;"
    on:click={() => (selected = "orange")}
  />
  <button
    aria-current={selected === "yellow"}
    aria-label="yellow"
    style="background: yellow;"
    on:click={() => (selected = "yellow")}
  />
  <button
    aria-current={selected === "green"}
    aria-label="green"
    style="background: green;"
    on:click={() => (selected = "green")}
  />
  <button
    aria-current={selected === "blue"}
    aria-label="blue"
    style="background: blue;"
    on:click={() => (selected = "blue")}
  />
  <button
    aria-current={selected === "indigo"}
    aria-label="indigo"
    style="background: indigo;"
    on:click={() => (selected = "indigo")}
  />
  <button
    aria-current={selected === "violet"}
    aria-label="violet"
    style="background: violet;"
    on:click={() => (selected = "violet")}
  />
</div> -->

<!-- <div>
  {#each colors as color, i}
    <button
      aria-current={selected === color}
      aria-label={color}
      style="background: {color}"
      on:click={() => (selected = color)}>{i + 1}</button
    >
  {/each}
</div> -->

<!-- {#each users as user (user.id)}
  <div>
    <h1>{user.name}</h1>
  </div>
{/each} -->

<!-- <button on:click={handleClick}>generate random number</button>

{#await promise}
  <p>Data is coming in</p>
{:then number}
  <p>The data is {@html number}</p>
{:catch error}
  <p>{@html error.messsage}</p>
{/await} -->

<!-- <div on:pointermove={handleMove}>
  The pointer is at {m.x} x {m.y}
</div> -->

<button on:click|once={() => alert("clicked")}>Click me</button>

<!-- <Inner on:message={handleMessage} /> -->

<Outer on:message={handleMessage} />

<BigRedButton on:click={handleClick} />

<!-- <input type="text" onchange={(e) => setInput(e.target.value)} /> -->

<input bind:value={name} />

<h1>Hello {name}!</h1>

<style>
  /* h1 {
    color: lightblue;
    transition: color 0.2s;
  } */

  /* div {
    display: grid;
    grid-template-columns: repeat(7, 1fr);
    grid-gap: 5px;
    max-width: 400px;
    position: fixed;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    padding: 1rem;
  } */

  /* button {
    aspect-ratio: 1;
    border-radius: 50%;
    background: var(--color, #fff);
    transform: translate(-2px, -2px);
    filter: drop-shadow(2px, 2px, 3px, rgba(0, 0, 0, 0.2));
    transition: all 0.1s;
  } */

  /* button[aria-current="true"] {
    transform: none;
    filter: none;
    box-shadow: inset 3px, 3px, 4px, rgba(0, 0, 0, 0.2);
  } */
</style>
