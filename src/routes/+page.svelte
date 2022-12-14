<script>

</script>

<div class="wrapper">
  <h2>Svelte Scrolly Playground</h2>
  <p>Welcome! This is a space to test out different styles of scrolling-storytelling.</p>
  <nav>
    <a href="/sticky">Sticky Studies</a>
    <a href="/ocean">Ocean Dive</a>
    <a href="/simple">Simple</a>
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
    margin-top: 20px;
  }
  p {
    color: white;
  }
  h2 {
    color: white;
    margin-top: 0px;
    margin-bottom: 10px;
  }
  a {
    background-color: white;
    padding: 20px;
    border: 1px solid lightgray;
    box-shadow: 0px 2px 4px 0px rgba(0,0,0,0.1); 
    position: static;
    z-index: 1000;
    color: black;
    margin: 0px 5px;
  }
</style>

