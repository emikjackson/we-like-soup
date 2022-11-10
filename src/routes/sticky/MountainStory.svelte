<script>
  import Scrolly from "$lib/components/Scrolly.svelte";
  import Scene from "../../lib/components/graphics/Scene.svelte";
  import HeaderBlock from "./HeaderBlock.svelte";
  import Section from "./Section.svelte";
  import Tile from "./Tile.svelte";
  let stepIndex = 0;
  const bgColor = "#ebebeb";

  const hill1Paths = [
    "M214.5,692 C261.36054,655.074833 289.693874,611.408166 299.5,561 L416.5,486 L521,670.5 L652.5,797 L0,797 C96.1394598,763.925167 167.63946,728.925167 214.5,692 Z",
    "M140.5,592 L217,515 C224.403422,533.074636 238.570088,564.741302 259.5,610 C280.429912,655.258698 325.263245,700.425364 394,745.5 L652.5,797 L0,797 L140.5,592 Z",
  ]
  const hill2Paths = [
    "M139.5,550.5 L218.5,366 C231.236755,450.407969 248.070088,515.241302 269,560.5 C289.929912,605.758698 331.596578,667.425364 394,745.5 L652.5,797 L0,797 L139.5,550.5 Z",
    "M219,673 C270.28879,617.902198 293.78879,555.568865 289.5,486 L420,342 L517.5,486 L652.5,797 L0,797 C94.7112101,769.431135 167.71121,728.097802 219,673 Z",
  ]

  const moonPathHidden = "M332,783 C355.685792,783 376.543151,770.89004 388.718312,752.523888 C353.906104,756.841296 330,747 317,723 C304,699 309,673.666667 332,647 C294.444637,647 264,677.444637 264,715 C264,752.555363 294.444637,783 332,783 Z";
  const moonPathVisible = "M326,287 C349.685792,287 370.543151,274.89004 382.718312,256.523888 C347.906104,260.841296 324,251 311,227 C298,203 303,177.666667 326,151 C288.444637,151 258,181.444637 258,219 C258,256.555363 288.444637,287 326,287 Z";
  
  const sunPathHidden = "M327,797 C358.480231,797 384,771.480231 384,740 C384,708.519769 358.480231,683 327,683 C310.982194,683 296.507545,689.607041 286.152664,700.244511 C276.156815,710.513151 270,724.537575 270,740 C270,771.480231 295.519769,797 327,797 Z";
  const sunPathVisible = "M326,259 C357.480231,259 383,233.480231 383,202 C383,170.519769 357.480231,145 326,145 C309.018107,145 293.770722,152.426311 283.328267,164.20851 C274.412992,174.267596 269,187.501662 269,202 C269,233.480231 294.519769,259 326,259 Z";

  const daySky = ['#B3E3EA', '#F0F5F6'];
  const sunsetSky = ['#198D9F', '#E18B4C'];
  const nightSky = ['#0F5478', '#0E1F39'];

  const dayHills = [
    ['#897969', '#47392F'],
    ['#937151', '#573922']
  ]

  const sunsetHills = [
    ['#524233', '#1F1812'],
    ['#5C4228', '#3F2614']
  ]

  const nightHills = [
    ['#1F1441', '#150C1C'],
    ['#232662', '#05060C']
  ]
  

  let sceneSteps = [
    { 
      hill1Path: hill1Paths[0],
      hill2Path: hill2Paths[0],
      moonPath: moonPathHidden,
      sunPath: sunPathVisible,
      skyGradient: daySky,
      hill1Gradient: dayHills[0],
      hill2Gradient: dayHills[1]
    },
    { 
      hill2Path: hill1Paths[1],
      hill1Path: hill2Paths[1],
      moonPath: moonPathHidden,
      sunPath: sunPathVisible,
      skyGradient: daySky,
      hill1Gradient: dayHills[0],
      hill2Gradient: dayHills[1]
    },
    { 
      hill1Path: hill1Paths[0],
      hill2Path: hill2Paths[0],
      moonPath: moonPathHidden,
      sunPath: sunPathHidden,
      skyGradient: sunsetSky,
      hill1Gradient: sunsetHills[0],
      hill2Gradient: sunsetHills[1]
    },
    { 
      hill1Path: hill1Paths[0],
      hill2Path: hill2Paths[0],
      moonPath: moonPathVisible,
      sunPath: sunPathHidden,
      skyGradient: nightSky,
      hill1Gradient: nightHills[0],
      hill2Gradient: nightHills[1]
    },
  ]

  const sceneWidth = 400;
  const tileWidth = 400;
  const sceneHeight = 488;
</script>

<HeaderBlock {bgColor}>
  <h2>Next, let's try some side-by-side action.</h2>
  <p>Two-column view when on desktop, back to overlap on smaller screens.</p>
</HeaderBlock>

<Section {bgColor}>
  <div class="sticky">
    <div class="offset" style={`width:${tileWidth}px;`} />
    <Scene width="400px" height="488px" {...sceneSteps[stepIndex]} />
  </div>
  <div class="text mobile-offset">
    <Scrolly bind:value={stepIndex}>
      {#each sceneSteps as _, i}
        <Tile style={`width:${tileWidth}px;`}>
          <h2>Example {i}</h2>
          <p>Lorem ipsum. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
        </Tile>
      {/each}
    </Scrolly>
    <div class="offset" style={`width:${sceneWidth}px;`} />
  </div>
</Section>

<style>
  .sticky {
    position: -webkit-sticky;
    position: sticky;
    top: 0;
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
    gap: 50px;
  }
  .text {
    display: flex;
    align-items: center;
    position: relative;
    z-index: 1;
    justify-content: center;
    gap: 50px;
    margin-top: -60vh;
  }
  .offset{
    height: 1px;
    display: block;
  }
  @media only screen and (max-width: 800px) {
    .offset{
      display: none;
    }
    .text {
      gap: 0px;
    }
  }
</style>