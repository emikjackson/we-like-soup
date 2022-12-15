<script>
  import { circOut} from 'svelte/easing';
  export let width = '850px';
  export let height = '850px';
  export let bowl_outer, bowl_inner, broth, spoon1, spoon2, toppings1, toppings2;

  function spin(node, options) {
    const duration = (options || {}).duration || 2000;
    const degrees = (options || {}).degrees || 360;
		return {
      duration: duration,
      easing: circOut,
			css(t) {
				return `transform: scale(${Math.min(t * 1.3, 1)}) rotate(${t * degrees}deg); opacity: ${t};`;
			}
		};
	}
</script>

<div style={`width:${width};height:${height};`} class="wrapper">
  <svg {width} {height} viewBox="0 0 850 850" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
    <defs>
      <radialGradient cx="-8.80883836%" cy="-19.1833764%" fx="-8.80883836%" fy="-19.1833764%" r="103.358631%" id="radialGradient-1">
        <stop stop-color="#FFFFFF" offset="0%"></stop>
        <stop stop-color="#FFFFFF" stop-opacity="0" offset="100%"></stop>
      </radialGradient>
    </defs>
    <g id="Page-4" stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
      <circle id="bowl_outer" fill={bowl_outer.fill} cx="424.5" cy="424.5" r={bowl_outer.r}></circle>
      <circle id="bowl_inner" fill={bowl_inner.fill}  cx="424.5" cy="424.5" r={bowl_inner.r}></circle>
      <circle id="broth" fill={broth.fill}  cx="424.5" cy="424.5" r={broth.r}></circle>
      <circle id="highlight" fill="url(#radialGradient-1)" cx="424.5" cy="424.5" opacity="0.562376476" r={broth.r - 25}></circle>
      <path id="spoon1" fill={spoon1.fill} d={spoon1.d}></path>
      <path id="spoon2" fill={spoon2.fill} d={spoon2.d}></path>
    </g>
  </svg>
  {#key toppings1}
    <img transition:spin style={`width:${width};height:${height};`} src={toppings1} alt="" />
  {/key}
  {#key toppings2}
    <img transition:spin={{ duration: 2500, degrees: 720 }} style={`width:${width};height:${height};`} src={toppings2} alt="" />
  {/key}
</div>

<style>

  .wrapper {
    position: relative;
  }

  path, circle {
    transition: all 1s ease;
  }

  img {
    position: absolute;
    z-index: 1;
    top: 0px;
    left: 0px;
    opacity: 1;
  }

</style>