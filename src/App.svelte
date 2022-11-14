<script>
  import HashRouting from "./HashRouting.svelte";
  import PageJs from "./PageJs.svelte";
  import Problem from "./Problem.svelte";
  export let pageName;
  const query = new URLSearchParams(window.location.search);
  pageName = query.get("page");
</script>

<main>
  {#if pageName === "problem"}
    <Problem />
  {:else}
    <!-- <PageJs /> -->
    <HashRouting />
  {/if}
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
