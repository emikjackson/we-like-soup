<script>
  export let bgColor = "#fefefe";
</script>

<div style={`background-color:${bgColor};`}>
  <slot />  
</div>

<style>
  div {
    width: 100%;
  }
</style>