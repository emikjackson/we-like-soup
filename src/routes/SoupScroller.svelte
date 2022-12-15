<script>
  import Scrolly from "$lib/components/Scrolly.svelte";
  import Section from "$lib/components/Section.svelte";
  import Tile from "$lib/components/Tile.svelte";
  import SoupBowl from "./SoupBowl.svelte";

  import soup1_toppings1 from "$lib/assets/soup1_toppings1.svg";
  import soup1_toppings2 from "$lib/assets/soup1_toppings2.svg";
  import soup2_toppings1 from "$lib/assets/soup2_toppings1.svg";
  import soup2_toppings2 from "$lib/assets/soup2_toppings2.svg";
  import soup3_toppings1 from "$lib/assets/soup3_toppings1.svg";
  import soup3_toppings2 from "$lib/assets/soup3_toppings2.svg";
  import soup4_toppings1 from "$lib/assets/soup4_toppings1.svg";
  import soup4_toppings2 from "$lib/assets/soup4_toppings2.svg";
  import soup5_toppings1 from "$lib/assets/soup5_toppings1.svg";
  import soup5_toppings2 from "$lib/assets/soup5_toppings2.svg";
  import soup6_toppings1 from "$lib/assets/soup6_toppings1.svg";
  import soup6_toppings2 from "$lib/assets/soup6_toppings2.svg";

  let index = 0;
  const bgColor = "#ebebeb";

  let soups = [
    // Gerard's kale soup
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
      title: "Kale soup with potatoes and sausage",
      paragraphs: ["Best served with a crunchy baguette.", "A spicy chorizo adds some heat to this delectable soup."],
      link: "https://cooking.nytimes.com/recipes/7416-kale-soup-with-potatoes-and-sausage",
      toppings1: soup1_toppings1,
      toppings2: soup1_toppings2,
    },
    // Emi's fishy fridge soup
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
    // Carly's butternut squash soup
    { 
      bowl_outer: {
        fill: "#A65DB0",
        r: 372
      },
      bowl_inner: {
        fill: "#5B3960",
        r: 355
      },
      broth: {
        fill: "#F7AF3F",
        r: 309
      },
      spoon1: {
        fill: "#DCDCDC",
        d: "M493.5,195.119491 C556.833333,72.706497 594,9.5 605,5.5 C621.5,-0.5 620.593846,-2.92804049 642.5,13.1194911 C664.406154,29.1670226 665.5,39.5 665.5,52.5 C665.5,61.1666667 616.666667,115.206497 519,214.619491 L493.5,195.119491 Z"
      },
      spoon2: {
        fill: "#BFBFBF",
        d: "M506,204.119491 C591.666667,76.7861577 637.166667,13.1194911 642.5,13.1194911 C650.5,13.1194911 665.5,39.5 665.5,52.5 C665.5,61.1666667 616.666667,115.206497 519,214.619491 L506,204.119491 Z",
      },
      title: "Butternut squash soup",
      paragraphs: ["This fall classic works equally well in wintertime.", "Though the plain soup speaks well enough for itself, feel free to spruce it up with some black pepper and a sprig of rosemary."],
      // link: "https://cooking.nytimes.com/recipes/7416-kale-soup-with-potatoes-and-sausage",
      toppings1: soup3_toppings1,
      toppings2: soup3_toppings2,
    },
    // David's Vegetable Maafé soup
    { 
      bowl_outer: {
        fill: "#D0AC42",
        r: 373
      },
      bowl_inner: {
        fill: "#706133",
        r: 342
      },
      broth: {
        fill: "#C1631E",
        r: 301
      },
      spoon1: {
        fill: "#473737",
        d: "M538.5,194.119491 C606.5,87.0398304 644.666667,27.5 653,15.5 C665.5,-2.5 665.593846,-3.92804049 687.5,12.1194911 C709.406154,28.1670226 687.5,33.5 687.5,46.5 C687.5,55.1666667 645.833333,110 562.5,211 L538.5,194.119491 Z"
      },
      spoon2: {
        fill: "#281D1D",
        d: "M551,203.119491 C636.666667,75.7861577 682.166667,12.1194911 687.5,12.1194911 C695.5,12.1194911 708,26.5 697,40 C689.666667,49 645.333333,106.873164 564,213.619491 L551,203.119491 Z",
      },
      title: "Vegetable Maafé Soup",
      paragraphs: [
        "This West African peanut stew brings home all the cozy flavors you need to get warm after walking your dog in the bitter cold: peanuts, ginger, sweet potatoes, a spicy scotch bonnet.",
        "And it's vegetarian! Serve with rice or eat on its own.",
      ],
      link: "https://www.google.com/url?q=https://cooking.nytimes.com/recipes/1023570-vegetable-maafe?smid%3Dck-recipe-iOS-share&sa=D&source=editors&ust=1671138013692856&usg=AOvVaw0BZlz7UJzytLk-m9Lri49b",
      toppings1: soup4_toppings2,
      toppings2: soup4_toppings1,
    },
    // Taylor's budae jjigae
    { 
      bowl_outer: {
        fill: "#CBB397",
        r: 393
      },
      bowl_inner: {
        fill: "#AB8C6A",
        r: 365
      },
      broth: {
        fill: "#EA6842",
        r: 334
      },
      spoon1: {
        fill: "#DCDCDC",
        d: "M629.506173,192.073852 C718.675848,65.6513073 764.343718,2.07985649 766.509783,1.35950011 C769.75888,0.278965533 769.217364,0.14985129 772.466462,1.35950011 C775.715559,2.56914892 779.506173,2.44003468 779.506173,10.0037767 C779.506173,15.0462714 733.477292,79.8783458 641.41953,204.5 L629.506173,192.073852 Z"
      },
      spoon2: {
        fill: "#BFBFBF",
        d: "M633.506173,195.450833 C720.374039,66.1502778 766.679638,1.5 772.422968,1.5 C781.037963,1.5 780.499525,6.35904255 780.499525,10.1382979 C780.499525,12.6578014 734.373406,77.4450355 642.121168,204.5 L633.506173,195.450833 Z",
      },
      title: "Budae Jjigae (Army Stew)",
      paragraphs: ["A korean hot pot dish with mandatory american cheese."],
      link: "https://mykoreankitchen.com/army-stew-budae-jjigae/",
      toppings1: soup5_toppings2,
      toppings2: soup5_toppings1,
    },
    // Brian's white bean & kale
    { 
      bowl_outer: {
        fill: "#6C9837",
        r: 373
      },
      bowl_inner: {
        fill: "#475F2B",
        r: 342
      },
      broth: {
        fill: "#E8BF4B",
        r: 301
      },
      spoon1: {
        fill: "#ECECEC",
        d: "M538.5,188.119491 C597.5,94.0398304 631.166667,41 639.5,29 C652,11 665.593846,-9.92804049 687.5,6.11949108 C709.406154,22.1670226 687.5,27.5 687.5,40.5 C687.5,49.1666667 645.833333,104 562.5,205 L538.5,188.119491 Z"
      },
      spoon2: {
        fill: "#D1D1D1",
        d: "M551,197.119491 C636.666667,69.7861577 682.166667,6.11949108 687.5,6.11949108 C695.5,6.11949108 708,36 697,49.5 C689.666667,58.5 645.333333,111.206497 564,207.619491 L551,197.119491 Z",
      },
      title: "White bean and kale with homemade chicken stock",
      paragraphs: ["Brian's homemade creation features rosemary, lemon thyme, Parmesan, greens from his garden, and stock from the one chicken soup he makes a year and keeps in his freezer for unforseen sickness."],
      toppings1: soup6_toppings2,
      toppings2: soup6_toppings1,
    },
  ]

  const sceneWidth = 450;
  const tileWidth = 350;
  const sceneHeight = 488;
</script>

<Section {bgColor}>
  <div class="sticky">
    <SoupBowl width="450px" height="550px" {...soups[index]} />
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
          {#if soup.link}
            <p>
              <a href={soup.link} target="_blank" rel="noopener noreferrer">Try the recipe</a>
            </p>
          {/if}
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