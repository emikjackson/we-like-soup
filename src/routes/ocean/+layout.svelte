<script>
  import { distance } from '$lib/stores/distance.js'

  // set overall scroll distance
  const onScroll = () => {
    distance.set(window.scrollY);
  }
</script>

<svelte:window on:scroll={onScroll}/>

<slot />