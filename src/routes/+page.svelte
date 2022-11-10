<script>

</script>

<div class="wrapper">
  <h2>Svelte Scrolly Playground</h2>
  <nav>
    <a href="/ocean">Ocean</a>
    <!-- <a href="/blob">Blob</a> -->
    <a href="/sticky">Sticky</a>
  </nav>
</div>

<style>
  .wrapper {
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
  }
  nav {
    margin-bottom: 40px;
  }
  h2 {
    color: white;
    margin-top: 0px;
  }
  a {
    background-color: white;
    padding: 20px;
    border: 1px solid lightgray;
    box-shadow: 0px 2px 4px 0px rgba(0,0,0,0.1); 
    position: static;
    z-index: 1000;
    color: black;
  }
</style>

