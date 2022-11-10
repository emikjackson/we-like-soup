<script>
  import Circle from "$lib/components/graphics/Circle.svelte";
  import { onMount } from 'svelte';
  import Text from "$lib/components/Text.svelte";
  import Zoomer from "$lib/components/zoomer/Zoomer.svelte";

  let height = 11000; // Appx 4 desktop screen lengths
  let screenWidth = 0;
  let screenHeight = 0;
  const NUM_CIRCLES = 100;

  onMount(() => {
    screenWidth = screen.width;
    screenHeight = screen.height;
  })
</script>

{#each { length: NUM_CIRCLES } as _, i}
  {@const initBottom = -(Math.random() * 5000)}
  {@const initLeft = Math.random() * screenWidth}
  {@const speed = (Math.random() * 2) + 0.7}
  {@const width = (150/speed) + 10}
  <Circle {initBottom} {initLeft} {speed} {width} />
{/each}

<Text start={0} end={1500}>
  Deep in the ocean ...
</Text>
<Text start={2000} end={3500}>
  Far below the surface ...
</Text>
<Text start={4000} end={5500}>
  Things start to get ...
</Text>
<Text start={7000} end={10000} jitteryText="FUNKY ... !!!" />

<Zoomer start={7500} end={10000} maintain={11000} />

<Text start={10000} end={11000} style={"left:50%;border-radius:50%;"}>
  Well hello!
</Text>

<div class="moving-bg" style={`height:${height}px;`} />

<style>
  .moving-bg {
    height: 400vh;
    width: 100%;
    background-image: linear-gradient(rgb(9, 47, 68), black);
    /* border-left: 5px dashed black; */
  }
</style>