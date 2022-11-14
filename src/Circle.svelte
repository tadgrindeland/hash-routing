<script>
  export let radius = 100;
  export let color = "red";
</script>

<div class="wrapper">
  <p>The Circle 'Page'</p>
  <span
    class="circle"
    style="background-color:{color}; height:{radius}px; width:{radius}px"
  />
</div>

<style>
  .circle {
    border-radius: 50%;
    display: inline-block;
    margin-bottom: 3rem;
  }

  p {
    font-size: 50px;
  }
</style>
