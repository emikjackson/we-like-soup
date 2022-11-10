<script>
  export let bgColor = "#fefefe";
</script>

<div style={`background-color:${bgColor};`}>
  <slot />  
</div>

<style>
  div {
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    padding: 40px 20px;
    box-sizing: border-box;
  }
</style>