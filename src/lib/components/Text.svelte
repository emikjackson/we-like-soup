<script>
  import { fade } from 'svelte/transition';
  import { distance } from '$lib/stores/distance';
  export let style = "";
  export let start;
  export let end;
  export let jitteryText; // just super extra
</script>

{#if $distance > start && $distance < end}
  <p class="fixed" transition:fade {style}>
    {#if jitteryText}
      {#each jitteryText as letter, i}
        <span class="jittery" style={`animation-delay:${(i*100)+70}ms;`}>
          {letter}
        </span>
      {/each}
    {:else}
      <slot />
    {/if}
  </p>
{/if}

<style>
  @keyframes jitter { 
    50% {
      transform: skewY(8deg) skewX(-8deg) translateX(1px) translateY(1px) scale(1);
    } 
  }
  span.jittery {
    animation: jitter 200ms linear infinite; 
    display:inline-block;
    font-size: 1.5rem;
  }
  .fixed {
    background-color: white;
    padding: 20px;
    border: 1px solid lightgray;
    box-shadow: 0px 2px 4px 0px rgba(0,0,0,0.1);
    position: fixed;
    left: 200px;
    top: 40vh;
    z-index: 1000;
  }
</style>