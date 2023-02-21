<script>
  // Animated spoon & shadow SVGs, rotating on a set interval
  import { onInterval } from '$lib/utils/helpers.js';

  export let interval = 1500;

  let width = 400;
  let height = 300;
  let index = 0;

  // SVG display information for each spoon type.
  // Each object has the path outline (d) & fill for the spoon and shadow.
  const spoons = [
    {
      spoon: { 
        d: "M709,34 C672,44 295.5,346 266,361.5 C236.5,377 164.5,340 115.5,369.5 C66.5,399 18.5,465 68,527 C117.5,589 223.5,577 266,527 C308.5,477 260.5,423 304.5,395.5 C348.5,368 746.5,98 751.5,71 C756.5,44 746,24 709,34 Z",
        fill: "#8DD9E1",
      },
      shadow: {
        d: "M82,514.5 C48.5,476 75.5519018,411.76164 118.5,391 C147.132065,377.158907 190.465399,377.158907 248.5,391 C268.5,459 262,503.833333 229,525.5 C179.5,558 115.5,553 82,514.5 Z",
        fill: "#70C1CA",
      }
    },
    {
      spoon: { 
        d: "M681.5,44.5 C644.5,54.5 326.5,342 297,357.5 C267.5,373 160,355 111,384.5 C62,414 0.0338869929,501.317642 36,534.5 C71.966113,567.682358 198.493313,565.800756 267.5,534.5 C336.506687,503.199244 290.5,423.5 334.5,396 C378.5,368.5 769.5,104.5 774.5,77.5 C779.5,50.5 718.5,34.5 681.5,44.5 Z",
        fill: "#ABB1B3",
      },
      shadow: {
        d: "M51,519 C27.5,489 93.5519018,419.76164 136.5,399 C165.132065,385.158907 213.132065,381.99224 280.5,389.5 C297.731477,454.051608 286.231477,496.051608 246,515.5 C185.652784,544.672588 74.5,549 51,519 Z",
        fill: "#9BA4A7",
      }
    },
    {
      spoon: { 
        d: "M653,118 C616,128 485.5,255 456,270.5 C426.5,286 339.5,290 283.5,304 C227.5,318 106.5,366.5 106.5,413.5 C106.5,460.5 285.5,507.5 383.5,472.5 C481.5,437.5 464,341 510.5,299 C557,257 668.5,151 702.5,140.5 C736.5,130 690,108 653,118 Z",
        fill: "#E0D584",
      },
      shadow: {
        d: "M136,414 C114,403 138,387.5 213.5,348.5 C263.833333,322.5 341.166667,306.333333 445.5,300 C458.166667,341.333333 421.333333,373.5 335,396.5 C205.5,431 158,425 136,414 Z",
        fill: "#C4B85F",
      }
    }
  ]

  // On a set interval, update the index to change the displayed spoon
  onInterval(() => index = (index + 1)%(spoons.length), interval);

</script>

<svg width={`${width}px`} height={`${height}px`} viewBox="0 0 800 600" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
  <g stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
      <path d={spoons[index].spoon.d} fill={spoons[index].spoon.fill} id="spoon"></path>
      <path d={spoons[index].shadow.d} fill={spoons[index].shadow.fill} id="shadow"></path>
  </g>
</svg>

<style>
  path {
    stroke-width: 2px;
    transition: all 1s ease;
  }
</style>