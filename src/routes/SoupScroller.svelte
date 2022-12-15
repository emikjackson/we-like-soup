<script>
  import Scrolly from "$lib/components/Scrolly.svelte";
  import Section from "$lib/components/Section.svelte";
  import Tile from "$lib/components/Tile.svelte";
  import SoupBowl from "./SoupBowl.svelte";

  import soup1_toppings1 from "$lib/assets/soup1_toppings1.svg";
  import soup1_toppings2 from "$lib/assets/soup1_toppings2.svg";
  import soup2_toppings1 from "$lib/assets/soup2_toppings1.svg";
  import soup2_toppings2 from "$lib/assets/soup2_toppings2.svg";

  let index = 0;
  const bgColor = "#ebebeb";

  let soups = [
    { 
      bowl_outer: {
        fill: "#E86F48",
        r: 376
      },
      bowl_inner: {
        fill: "#924A33",
        r: 335
      },
      broth: {
        fill: "#F3D163",
        r: 309
      },
      spoon1: {
        fill: "#AAAAAA",
        d: "M545.5,230 C602.5,98.3333333 636.5,30.5 647.5,26.5 C664,20.5 672.593846,31.9524684 694.5,48 C716.406154,64.0475316 733.5,76.5 733.5,89.5 C733.5,98.1666667 679.333333,151.5 571,249.5 L545.5,230 Z"
      },
      spoon2: {
        fill: "#868686",
        d: "M558,239 C643.666667,111.666667 689.166667,48 694.5,48 C702.5,48 733.5,76.5 733.5,89.5 C733.5,98.1666667 679.333333,151.5 571,249.5 L558,239 Z",
      },
      title: "Portuguese Kale Soup",
      paragraphs: ["Kale soup with potatoes and sausage.", "Best served with xyz", "Lorem ipsum"],
      toppings1: soup1_toppings1,
      toppings2: soup1_toppings2,
    },
    { 
      bowl_outer: {
        fill: "#1895A7",
        r: 332
      },
      bowl_inner: {
        fill: "#235E67",
        r: 309
      },
      broth: {
        fill: "#8C7C58",
        r: 274
      },
      spoon1: {
        fill: "#BB8457",
        d: "M555.5,254.119491 C620.166667,119.373164 658,50 669,46 C685.5,40 687.5,39.5 693,46 C698.5,52.5 698.5,51.5 698.5,64.5 C698.5,73.1666667 656.5,139 572.5,262 L555.5,254.119491 Z"
      },
      spoon2: {
        fill: "#BB8457",
        d: "M581.5,269.5 C679.5,144.5 731.166667,82 736.5,82 C744.5,82 753.5,88 753.5,101 C753.5,109.666667 701.333333,169.666667 597,281 L581.5,269.5 Z"
      },
      title: "Fishy Fridge",
      paragraphs: ["Fridge veggies (mushrooms, squash, yams), tossed into a dashi broth with soba."],
      toppings1: soup2_toppings1,
      toppings2: soup2_toppings2,
    },
  ]

  const sceneWidth = 400;
  const tileWidth = 400;
  const sceneHeight = 488;
</script>

<Section {bgColor}>
  <div class="sticky">
    <SoupBowl width="400px" height="488px" {...soups[index]} />
    <div class="offset" style={`width:${tileWidth}px;`} />
  </div>
  <div class="text mobile-offset">
    <div class="offset" style={`width:${sceneWidth}px;`} />
    <Scrolly bind:value={index}>
      {#each soups as soup, i}
        <Tile style={`width:${tileWidth}px;`}>
          <h2>{soup.title}</h2>
          {#each soup.paragraphs as line}
            <p>{line}</p>
          {/each}
        </Tile>
      {/each}
    </Scrolly>
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