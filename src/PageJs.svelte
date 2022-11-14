<script>
  import Circle from "./Circle.svelte";
  import NotFound from "./NotFound.svelte";
  import Square from "./Square.svelte";
  import Rectangle from "./Rectangle.svelte";
  import page from "page";

  let radius = "100";
  let length = "100";
  let color = "blue";

  let component;

  page.redirect("/", "/circle");
  page("/circle", () => (component = Circle));
  page("/square", () => (component = Square));
  page("/rectangle", () => (component = Rectangle));

  page("*", () => (component = NotFound));

  page.start();
</script>

<nav>
  <a href="/circle" class:active={component === Circle}>Circle</a>
  <a href="/square" class:active={component === Square}>Square </a>
  <a href="/rectangle" class:active={component === Rectangle}>Rectangle </a>
</nav>

<!-- <button on:click={() => (window.location.href = "/#page3")}>Test</button> -->
<!-- <label for="radius">Radius</label>
<select disabled={component !== Circle} name="radius" bind:value={radius}>
  <option value="100">100px</option>
  <option value="200">200px</option>
  <option value="300">300px</option>
  <option value="400">400px</option>
</select>

<label for="length">Length</label>
<select disabled={component !== Square} name="length" bind:value={length}>
  <option value="100">100px</option>
  <option value="200">200px</option>
  <option value="300">300px</option>
  <option value="400">400px</option>
</select>

<label for="color">Color</label>
<select name="color" bind:value={color}>
  <option value="red">Red</option>
  <option value="blue">Blue</option>
  <option value="green">Green</option>
  <option value="purple">Purple</option>
</select> -->
<main>
  <svelte:component this={component} bind:radius bind:color bind:length />
</main>

<style>
  :root {
    --space: 0.5rem;
  }

  a {
    background-color: white;
    border-radius: var(--space);
    margin-right: var(--space);
    padding: var(--space);
    text-decoration: none;
  }

  a.active {
    background-color: yellow;
  }

  .icon {
    padding-bottom: 6px;
    padding-top: 6px;
  }

  main {
    padding: var(--space);
  }

  nav {
    display: flex;
    align-items: center;
    background-color: cornflowerblue;
    padding: var(--space);
    margin-bottom: 1rem;
  }

  select {
    margin: 1rem;
  }
</style>
