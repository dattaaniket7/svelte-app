<script>
  // let name = "Stuart <button>Minnion</button>";
  // import src from "./assets/giphy.gif";
  // import Nested from "./lib/Nested.svelte";
  // import PackageInfo from "./lib/PackageInfo.svelte";
  // import { getRandomNumber } from "./lib/utils";
  // import Inner from "./lib/Inner.svelte";
  // import Outer from "./lib/Outer.svelte";
  // import BigRedButton from "./lib/BigRedButton.svelte";
  // import horn from "./assets/horn.mp3";
  // import { marked } from "marked";
  // import { onMount } from "svelte";
  // import Eliza from "elizabot";
  // import { beforeUpdate, afterUpdate } from "svelte";
  import { tick } from "svelte";

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

  // let users = [
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

  // function handleMessage(event) {
  //   alert(event.detail.text);
  // }

  // const audio = new Audio();
  // audio.src = horn;

  // function handleClick() {
  //   audio.play();
  // }

  // let name = "world";

  // let a = 1;
  // let b = 2;

  // let yes = false;

  // let questions = [
  //   {
  //     id: 1,
  //     text: `Where did you go to school?`,
  //   },
  //   {
  //     id: 2,
  //     text: `What is your mother's name?`,
  //   },
  //   {
  //     id: 3,
  //     text: `What is another personal fact that an attacker could easily find with Google?`,
  //   },
  // ];

  // let selected;

  // let answer = "";

  // function handleSubmit() {
  //   alert(
  //     `answered question ${selected.id} (${selected.text}) with "${answer}"`
  //   );
  // }

  // let scoops = 1;
  // let flavours = [];

  // const formatter = new Intl.ListFormat("en", {
  //   style: "long",
  //   type: "conjunction",
  // });

  // let value = `Some words are *italic*, some are **bold**\n\n- lists\n- are \n- cool`;

  // let newUser = "";

  // function addUser() {
  //   users = [...users, { name: newUser, id: crypto.randomUUID() }];
  //   newUser = "";
  // }

  // onMount(() => {
  //   console.log(users);
  // });

  // let div;
  // let autoscroll = false;

  // beforeUpdate(() => {
  //   if (div) {
  //     const scrollableDistance = div.scrollHeight - div.offsetHeight;
  //     autoscroll = div.scrollTop > scrollableDistance - 20;
  //   }
  // });

  // afterUpdate(() => {
  //   if (autoscroll) {
  //     div.scrollTo(0, div.scrollHeight);
  //   }
  // });

  // const eliza = new Eliza();
  // const pause = (ms) => new Promise((fulfil) => setTimeout(fulfil, ms));

  // const typing = { author: "eliza", text: "..." };

  // let comments = [];

  // async function handleKeydown(event) {
  //   if (event.key === "Enter" && event.target.value) {
  //     const comment = {
  //       author: "user",
  //       text: event.target.value,
  //     };

  //     const reply = {
  //       author: "eliza",
  //       text: eliza.transform(comment.text),
  //     };

  //     event.target.value = "";
  //     comments = [...comments, comment];

  //     await pause(200 * (1 + Math.random()));
  //     comments = [...comments, typing];

  //     await pause(500 * (1 + Math.random()));
  //     comments = [...comments, reply].filter((comment) => comment !== typing);
  //   }
  // }

  let text = "Select some text and hit the tab key to toggle uppercase";

  async function handleKeydown(event) {
    if (event.key !== "Tab") return;

    event.preventDefault();

    const { selectionStart, selectionEnd, value } = this;
    const selection = value.slice(selectionStart, selectionEnd);

    const replacement = /[a-z]/.test(selection)
      ? selection.toUpperCase()
      : selection.toLowerCase();

    text =
      value.slice(0, selectionStart) + replacement + value.slice(selectionEnd);

    // this has no effect because the DOM hasn't updated yet
    await tick();
    this.selectionStart = selectionStart;
    this.selectionEnd = selectionEnd;
  }
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

<!-- <input type="text" bind:value={newUser} /> -->

<!-- <button on:click={addUser}>Add a new User</button> -->

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

<!-- <button on:click|once={() => alert("clicked")}>Click me</button> -->

<!-- <Inner on:message={handleMessage} /> -->

<!-- <Outer on:message={handleMessage} /> -->

<!-- <BigRedButton on:click={handleClick} /> -->

<!-- <input type="text" onchange={(e) => setInput(e.target.value)} /> -->

<!-- <input bind:value={name} />

<h1>Hello {name}!</h1> -->

<!-- <label>
  <input type="number" bind:value={a} min="0" max="10" />
  <input type="range" bind:value={a} min="0" max="10" />
</label>

<label>
  <input type="number" bind:value={b} min="0" max="10" />
  <input type="range" bind:value={b} min="0" max="10" />
</label>

<p>{a} + {b} = {a + b}</p> -->

<!-- <label>
  <input type="checkbox" bind:checked={yes} />
  Yes! Send me regular email spam
</label>

{#if yes}
  <p>Thank you. We will bombard your inbox and sell your personal details</p>
{:else}
  <p>
    You must opt in to continue. If you are not paying, you are the product.
  </p>
{/if}

<button disabled={!yes}>Subscribe</button> -->

<!-- <h2>Insecurity questions</h2>

<form on:submit|preventDefault={handleSubmit}>
  <select bind:value={selected} on:change={() => (answer = "")}>
    {#each questions as question}
      <option value={question}>{question.text}</option>
    {/each}
  </select>

  <input bind:value={answer} />

  <button disabled={!answer} type="submit"> Submit </button>
</form>

<p>
  selected question {selected ? selected.id : "[...waiting]"}
</p> -->

<!-- <h2>Size</h2> -->

<!-- {#each [1, 2, 3] as number}
  <label>
    <input type="radio" name="scoops" value={number} bind:group={scoops} />

    {number}
    {number === 1 ? "scoop" : "scoops"}
  </label>
{/each} -->

<!-- <h2>Flavours</h2> -->

<!-- <select multiple bind:value={flavours}>
  {#each ["cookies and cream", "mint choc chip", "raspberry ripple"] as flavour}
    <label>
    <input
      type="checkbox"
      name="flavours"
      value={flavour}
      bind:group={flavours}
    />

    {flavour}
  </label>
    <option>{flavour}</option>
  {/each}
</select> -->

<!-- {#if flavours.length === 0}
  <p>Please select at least one flavour</p>
{:else if flavours.length > scoops}
  <p>Can't order more flavours than scoops!</p>
{:else}
  <p>
    You ordered {scoops}
    {scoops === 1 ? "scoop" : "scoops"} of {formatter.format(flavours)}
  </p>
{/if} -->

<!-- <div class="grid">
  input
  <textarea bind:value />

  output
  <div>{@html marked(value)}</div>
</div> -->

<!-- <div class="container">
  <div class="phone">
    <div class="chat" bind:this={div}>
      <header>
        <h1>Eliza</h1>

        <article class="eliza">
          <span>{eliza.getInitial()}</span>
        </article>
      </header>

      {#each comments as comment}
        <article class={comment.author}>
          <span>{comment.text}</span>
        </article>
      {/each}
    </div>

    <input on:keydown={handleKeydown} />
  </div>
</div> -->

<textarea value={text} on:keydown={handleKeydown} />

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

  /* .grid {
    display: grid;
    grid-template-columns: 5em 1fr;
    grid-template-rows: 1fr 1fr;
    grid-gap: 1em;
    height: 100%;
  } */

  /* textarea {
    flex: 1;
    resize: none;
  } */

  /* .container {
    display: grid;
    place-items: center;
    height: 100%;
  } */

  /* .phone {
    display: flex;
    flex-direction: column;
    width: 100%;
    height: 100%;
  } */

  /* header {
    display: flex;
    flex-direction: column;
    height: 100%;
    padding: 4em 0 0 0;
    box-sizing: border-box;
  } */

  /* h1 {
    flex: 1;
    font-size: 1.4em;
    text-align: center;
  } */

  /* .chat {
    height: 0;
    flex: 1 1 auto;
    padding: 0 1em;
    overflow-y: auto;
    scroll-behavior: smooth;
  } */

  /* article {
    margin: 0 0 0.5em 0;
  } */

  /* .user {
    text-align: right;
  } */

  /* span {
    padding: 0.5em 1em;
    display: inline-block;
  } */

  /* .eliza span {
    background-color: var(--bg-1);
    border-radius: 1em 1em 1em 0;
    color: var(--fg-1);
  } */

  /* .user span {
    background-color: #0074d9;
    color: white;
    border-radius: 1em 1em 0 1em;
    word-break: break-all;
  } */

  /* input {
    margin: 0.5em 1em 1em 1em;
  } */

  /* @media (min-width: 400px) {
    .phone {
      background: var(--bg-2);
      position: relative;
      font-size: min(2.5vh, 1rem);
      width: auto;
      height: 36rem;
      aspect-ratio: 9 / 16;
      border: 0.2em solid #222;
      border-radius: 1em;
      box-sizing: border-box;
      filter: drop-shadow(1px 1px 0px #222) drop-shadow(2px 2px 0px #222)
        drop-shadow(3px 3px 0px #222);
    }

    .phone::after {
      position: absolute;
      content: "";
      background: #222;
      width: 60%;
      height: 1em;
      left: 20%;
      top: 0;
      border-radius: 0 0 0.5em 0.5em;
    }
  } */

  /* @media (prefers-reduced-motion) {
    .chat {
      scroll-behavior: auto;
    }
  } */

  textarea {
    width: 100%;
    height: 100%;
    resize: none;
  }
</style>
