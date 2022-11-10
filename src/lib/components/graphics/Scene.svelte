<script>
  export let width = '653px';
  export let height = '797px';
  export let skyGradient, hill1Gradient, hill2Gradient;
  export let moonPath, sunPath, hill1Path, hill2Path;
</script>

<svg {width} {height} viewBox="0 0 653 797" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
    <title>scene</title>
    <defs>
        <linearGradient x1="50%" y1="0%" x2="50%" y2="100%" id="linearGradient-1">
            <stop stop-color={skyGradient[0]} offset="0%"></stop>
            <stop stop-color={skyGradient[1]} offset="100%"></stop>
        </linearGradient>
        <linearGradient x1="50%" y1="0%" x2="50%" y2="100%" id="linearGradient-2">
            <stop stop-color="#FFE562" offset="0%"></stop>
            <stop stop-color="#EDC141" offset="100%"></stop>
        </linearGradient>
        <linearGradient x1="50%" y1="0%" x2="50%" y2="97.5417771%" id="linearGradient-3">
            <stop stop-color={hill2Gradient[0]} offset="0%"></stop>
            <stop stop-color={hill2Gradient[1]} offset="100%"></stop>
        </linearGradient>
        <linearGradient x1="50%" y1="0%" x2="50%" y2="100%" id="linearGradient-4">
            <stop stop-color={hill1Gradient[0]} offset="0%"></stop>
            <stop stop-color={hill1Gradient[1]} offset="100%"></stop>
        </linearGradient>
    </defs>
    <g id="Page-1" stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
        <g id="scene">
            <path d="M200,0 L453,0 C563.45695,8.1310969e-15 653,89.54305 653,200 L653,795 C653,796.104569 652.104569,797 651,797 L2,797 C0.8954305,797 1.3527075e-16,796.104569 0,795 L0,200 C-4.19487845e-14,89.54305 89.54305,4.8712322e-14 200,0 Z" id="sky" fill="url(#linearGradient-1)"></path>
            <path d={moonPath} id="moon" fill="#F7F6F2"></path>
            <path d={sunPath} id="sun" fill="url(#linearGradient-2)"></path>
            <path d={hill2Path} id="hill2" fill="url(#linearGradient-3)"></path>
            <path d={hill1Path} id="hill1" fill="url(#linearGradient-4)"></path>
        </g>
    </g>
</svg>

<style>
  path {
    transition: all 1s ease;
  }
  svg {
    border: 4px solid white;
    border-radius: 150px 150px 0px 0px;
    box-shadow: 0px 2px 8px 0px rgba(0, 0, 0, 0.1);
  }
</style>