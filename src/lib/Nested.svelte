<script>
  export let x = 0;
  export let y = 0;
  let x = 0;
  let y = 0;
  let mousePosition = { x: 0, y: 0 };
</script>

<h1>Nested Component</h1>
<div on:pointermove={(e) => (mousePosition = { x: e.clientX, y: e.clientY })}>
  <p>The mouse position is at x:{mousePosition.x} y:{mousePosition.y}</p>
</div>

<style>
  div {
    position: fixed;
    min-height: 100vh;
    width: 100%;
    left: 0;
    top: 0;
  }
</style>
