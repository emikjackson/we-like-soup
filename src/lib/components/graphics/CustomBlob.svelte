<script>
  export let width = "700px";
  export let height = "700px";
  export let d, fill, style, outerStyle;
</script>

<svg {width} {height} style={outerStyle} viewBox="0 0 500 500" preserveAspectRatio="none" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"  id="blobSvg">
  <g>
    <path class="blob" {style} {fill} {d}>
    </path>
  </g>
</svg>

<style>
  .blob {
    filter: blur(20px);
    transition: all 1s;
  }
  svg {
    transition: all 1s;
  }
</style>