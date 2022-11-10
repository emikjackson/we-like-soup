<script>
  import { onMount } from 'svelte';
  import OceanStory from './OceanStory.svelte';

  onMount(() => {
    // reset to top of page on refresh
    scroll(0,0)
  })

</script>

<OceanStory />


<!-- getBoundingClientRect -->