<script>
  import { onInterval } from '$lib/utils/helpers.js';

  export let interval = 1500;

  let width = 100;
  let height = 100;
  let value = "M50,0 L100,100 L0,100 L50,0 Z";

  let index = 0;

  const paths = [
    {
      spoon: { 
        d: "M712,137 C675,147 298.5,449 269,464.5 C239.5,480 167.5,443 118.5,472.5 C69.5,502 21.5,568 71,630 C120.5,692 226.5,680 269,630 C311.5,580 263.5,526 307.5,498.5 C351.5,471 749.5,201 754.5,174 C759.5,147 749,127 712,137 Z",
        fill: "#8DD9E1",
      },
      shadow: {
        d: "M85,617.5 C51.5,579 78.5519018,514.76164 121.5,494 C150.132065,480.158907 193.465399,480.158907 251.5,494 C271.5,562 265,606.833333 232,628.5 C182.5,661 118.5,656 85,617.5 Z",
        fill: "#70C1CA",
      }
    },
    {
      spoon: { 
        d: "M685.5,183.5 C648.5,193.5 330.5,481 301,496.5 C271.5,512 164,494 115,523.5 C66,553 4.03388699,640.317642 40,673.5 C75.966113,706.682358 202.493313,704.800756 271.5,673.5 C340.506687,642.199244 294.5,562.5 338.5,535 C382.5,507.5 773.5,243.5 778.5,216.5 C783.5,189.5 722.5,173.5 685.5,183.5 Z",
        fill: "#ABB1B3",
      },
      shadow: {
        d: "M55,658 C31.5,628 97.5519018,558.76164 140.5,538 C169.132065,524.158907 217.132065,520.99224 284.5,528.5 C301.731477,593.051608 290.231477,635.051608 250,654.5 C189.652784,683.672588 78.5,688 55,658 Z",
        fill: "#9BA4A7",
      }
    },
    {
      spoon: { 
        d: "M649,221 C612,231 481.5,358 452,373.5 C422.5,389 335.5,393 279.5,407 C223.5,421 102.5,469.5 102.5,516.5 C102.5,563.5 281.5,610.5 379.5,575.5 C477.5,540.5 460,444 506.5,402 C553,360 664.5,254 698.5,243.5 C732.5,233 686,211 649,221 Z",
        fill: "#E0D584",
      },
      shadow: {
        d: "M132,517 C110,506 134,490.5 209.5,451.5 C259.833333,425.5 337.166667,409.333333 441.5,403 C454.166667,444.333333 417.333333,476.5 331,499.5 C201.5,534 154,528 132,517 Z",
        fill: "#C4B85F",
      }
    }
  ]

  onInterval(() => index = (index + 1)%(paths.length), interval);

</script>

<div class="wrapper">
  <h2>'Tis the season of</h2>
  <h1>Soup</h1>

  <svg width="806px" height="806px" viewBox="0 0 806 806" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
    <g id="Page-4" stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
        <path d={paths[index].spoon.d} fill={paths[index].spoon.fill} id="spoon"></path>
        <path d={paths[index].shadow.d} fill={paths[index].shadow.fill} id="shadow"></path>
    </g>
  </svg>
</div>


<style>
  .wrapper {
    background-color: rgb(239, 241, 245);
    min-height: 70vh;
    padding: 20px;
    padding-bottom: 200px;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
  }

  path {
    stroke-width: 2px;
    transition: all 1s ease;
  }
</style>