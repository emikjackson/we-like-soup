<script>
  import { distance } from '$lib/stores/distance';
  import ActiveZoomer from "./ActiveZoomer.svelte";

  export let dimensions = ['bottom', 'right', 'width', 'height'];
  export let startDimensions = [400, -100, 0, 0];
  export let endDimensions = [150, 600, 500, 500];
  export let start, end, maintain; // e.g. 8000, 9000, 10000

  // TODO: instead of zoomer component can we do zoomer helper??

  $: active = $distance > start && $distance < maintain;  
</script>

{#if active}
  {@const length = end - start}
  {@const distancePassed = $distance - start}
  {@const percentPassed = distancePassed / length}
  <ActiveZoomer {startDimensions} {endDimensions} {dimensions} {percentPassed}>
    <slot />
  </ActiveZoomer>
{/if}