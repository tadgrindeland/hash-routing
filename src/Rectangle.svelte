<script>
  let height = 200;
  let width = 400;
  export let color = "red";
</script>

<div class="wrapper">
  <p>The Rectangle 'Page'</p>

  <span
    class="rectangle"
    style="background-color:{color}; height:{height}px; width:{width}px"
  />
</div>

<style>
  .rectangle {
    display: inline-block;
    margin-bottom: 3rem;
  }

  p {
    font-size: 50px;
  }
</style>
