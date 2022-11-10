<script>
  import Blob from "../graphics/Blob.svelte";

  export let startDimensions, endDimensions, dimensions;
  export let percentPassed; // value from 0 to 1;

  let xOffset, yOffset, width, height;

  // this is not the right word I would love to remember the right word!!
  const linearEbbing = (start, end, percent) => ((end - start) * percent) + start;

  $: xOffset = linearEbbing(startDimensions[0], endDimensions[0], percentPassed)
  $: yOffset = linearEbbing(startDimensions[1], endDimensions[1], percentPassed)
  $: width = linearEbbing(startDimensions[2], endDimensions[2], percentPassed)
  $: height = linearEbbing(startDimensions[3], endDimensions[3], percentPassed)
</script>

<div style={`${dimensions[0]}:${xOffset}px;${dimensions[1]}:${yOffset}px;opacity:${percentPassed + 0.1};`}>
  <Blob {width} {height} />
</div>

<style>
  div {
    position: fixed;
  }
</style>
