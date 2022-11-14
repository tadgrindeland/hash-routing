<script>
  import Circle from "./Circle.svelte";
  import Square from "./Square.svelte";
  import Rectangle from "./Rectangle.svelte";
  let radius = "100";
  let length = "100";
  let color = "blue";

  let component;
</script>

<nav>
  <a class:active={component === Circle} on:click={() => (component = Circle)}
    >Circle</a
  >
  <a on:click={() => (component = Square)} class:active={component === Square}
    >Square
  </a>
  <a
    on:click={() => (component = Rectangle)}
    class:active={component === Rectangle}
    >Rectangle
  </a>
</nav>

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
</style>
