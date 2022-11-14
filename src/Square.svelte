<script>
  export let length = 100;
  export let color = "red";
</script>

<div class="wrapper">
  <p>The Square 'Page'</p>

  <span
    class="square"
    style="background-color:{color}; height:{length}px; width:{length}px"
  />
</div>

<style>
  .square {
    display: inline-block;
    margin-bottom: 3rem;
  }

  p {
    font-size: 50px;
  }
</style>
