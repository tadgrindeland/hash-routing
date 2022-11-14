<script>
  import Circle from "./Circle.svelte";
  import Square from "./Square.svelte";
  import Rectangle from "./Rectangle.svelte";
  import { component } from "./stores.js";
  let radius = "100";
  let length = "100";
  let color = "blue";

  const hashMap = {
    "#circle": Circle,
    "#square": Square,
    "#rectangle": Rectangle,
  };
  $component = hashMap[location.hash];

  function hashChange() {
    $component = hashMap[location.hash] ?? hashMap["#circle"];
  }
</script>

<svelte:window on:hashchange={hashChange} />

<nav>
  <a href="/#circle" class:active={component === Circle}>Circle</a>
  <a href="/#square" class:active={component === Square}>Square </a>
  <a href="/#rectangle" class:active={component === Rectangle}>Rectangle </a>
</nav>

<main>
  {#if $component}
    <svelte:component this={$component} bind:radius bind:color bind:length />
  {/if}
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
