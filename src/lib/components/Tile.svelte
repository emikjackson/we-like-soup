<script>
  export let style = "";
</script>

<div {style}>
  <slot />  
</div>

<style>
  div {
    background-color: white;
    padding: 30px 20px;
    border: 1px solid lightgray;
    box-shadow: 0px 2px 4px 0px rgba(0,0,0,0.1); 
    position: relative;
    z-index: 1000;
    width: 400px;
    max-width: 100%;
    margin-bottom: 60vh;
    box-sizing: border-box;
  }
</style>