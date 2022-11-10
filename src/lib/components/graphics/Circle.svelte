<script>
  import { distance } from '$lib/stores/distance';
  export let width = 100;
  export let color = "";
  export let initBottom = 0;
  export let initLeft = 0;
  export let speed = 1; // 1 speed is the same as background, 0.01 is very slow, 200 is very fast

  $: bottom = ($distance * speed) + initBottom;
  // $: console.log(`bottom:${bottom}; initBottom:${initBottom}; speed: ${speed};`)
</script>

<div style={`bottom:${bottom}px;left:${initLeft}px;background-color:${color};width:${width}px;height:${width}px;z-index:${Math.round(width)};`}>
</div>

<style>
  div {
    background-color: #1d8282;
    box-shadow: 0px 2px 4px 0px rgba(0,0,0,0.1);
    border-radius: 100%;
    position: fixed;
    opacity: 0.7;
  }
</style>