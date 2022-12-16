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
  import soup7_toppings1 from "$lib/assets/soup7_toppings1.svg";
  import soup7_toppings2 from "$lib/assets/soup7_toppings2.svg";
  import soup8_toppings1 from "$lib/assets/soup8_toppings1.svg";
  import soup8_toppings2 from "$lib/assets/soup8_toppings2.svg";
  import soup9_toppings1 from "$lib/assets/soup9_toppings1.svg";
  import soup9_toppings2 from "$lib/assets/soup9_toppings2.svg";

  let index = 0;
  const bgColor = "#ebebeb";

  let soups = [
    // Gerard's kale soup
    { 
      bowl_outer: {
        fill: "#BB7C49",
        r: 362
      },
      bowl_inner: {
        fill: "#764A26",
        r: 336
      },
      broth: {
        fill: "#DDB04B",
        r: 309
      },
      spoon1: {
        fill: "#AAAAAA",
        d: "M554,165.619491 C601.666667,64.2861577 631,11.6194911 642,7.61949108 C658.5,1.61949108 656.593846,-0.928040488 678.5,15.1194911 C700.406154,31.1670226 698,42.6194911 698,55.6194911 C698,64.2861577 658.5,107.452824 579.5,185.119491 L554,165.619491 Z"
      },
      spoon2: {
        fill: "#8F8F8F",
        d: "M564.5,175.619491 C633.833333,69.2861577 671.166667,16.1194911 676.5,16.1194911 C684.5,16.1194911 700,40.1194911 700,53.1194911 C700,61.7861577 659.166667,106.119491 577.5,186.119491 L564.5,175.619491 Z",
      },
      submitter: "Gerard",
      title: "Kale Soup with Potatoes and Sausage",
      paragraphs: ["Best served with a crunchy baguette.", "A spicy chorizo adds some heat to this delectable soup."],
      link: "https://cooking.nytimes.com/recipes/7416-kale-soup-with-potatoes-and-sausage",
      toppings1: soup1_toppings1,
      toppings2: soup1_toppings2,
    },
    // Emi's fishy fridge soup
    { 
      bowl_outer: {
        fill: "#6696B4",
        r: 332
      },
      bowl_inner: {
        fill: "#354C5B",
        r: 309
      },
      broth: {
        fill: "#B38357",
        r: 274
      },
      spoon1: {
        fill: "#655144",
        d: "M555.5,254.119491 C620.166667,119.373164 658,50 669,46 C685.5,40 687.5,39.5 693,46 C698.5,52.5 698.5,51.5 698.5,64.5 C698.5,73.1666667 656.5,139 572.5,262 L555.5,254.119491 Z"
      },
      spoon2: {
        fill: "#8A7365",
        d: "M581.5,269.5 C679.5,144.5 731.166667,82 736.5,82 C744.5,82 753.5,88 753.5,101 C753.5,109.666667 701.333333,169.666667 597,281 L581.5,269.5 Z"
      },
      submitter: "Emi",
      title: "Veggie Soba",
      paragraphs: ["A quick and easy go to for when I want something to warm me up, stat.", "Toss some soba noodles in a dashi base with a variety of cooked veggies. My favorites include mushrooms, simmered squash, and yams."],
      toppings1: soup2_toppings2,
      toppings2: soup2_toppings1,
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
      submitter: "Carly",
      title: "Butternut Squash Soup",
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
      submitter: "David",
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
      submitter: "Taylor",
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
      submitter: "Brian",
      title: "Tuscan White Bean Soup",
      paragraphs: ["Kale, Rosemary, and Lemon Thyme from my garden. Chicken stock from the one time a year I make chicken noodle soup to keep in the freezer in case of illness.", "Best served with homemade sourdough and good olive oil. Mmmm."],
      toppings1: soup6_toppings2,
      toppings2: soup6_toppings1,
    },
    // Jeff's Lentil
    { 
      bowl_outer: {
        fill: "#6E9A59",
        r: 345
      },
      bowl_inner: {
        fill: "#466139",
        r: 329
      },
      broth: {
        fill: "#A26A1F",
        r: 290
      },
      spoon1: {
        fill: "#666666",
        d: "M555,187.619491 C613,86.8731637 649.5,35.1666667 664.5,32.5 C687,28.5 698.5,-1.61949108 711.5,8 C724.5,17.6194911 698.5,45.5 698.5,58.5 C698.5,67.1666667 658.666667,115.833333 579,204.5 L555,187.619491 Z"
      },
      spoon2: {
        fill: "#464646",
        d: "M568,196.5 C658.333333,74.8333333 706.166667,14 711.5,14 C719.5,14 708.5,34 711.5,52 C713.5,64 670,115.666667 581,207 L568,196.5 Z",
      },
      submitter: "Jeff",
      title: "Lentil Soup",
      paragraphs: ["Few dishes achieve the trifecta of comforting, hearty, and nutritious quite like lentil soup.", "With so many types of lentils and supporting-ingredients to add, you have no excuse to not try a new lentil soup soon."],
      toppings1: soup9_toppings2,
      toppings2: soup9_toppings1,
    },
    // Shannon's Gumbo
    { 
      bowl_outer: {
        fill: "#BDCFD3",
        r: 366
      },
      bowl_inner: {
        fill: "#788A8E",
        r: 342
      },
      broth: {
        fill: "#985007",
        r: 312
      },
      spoon1: {
        fill: "#D0D0D0",
        d: "M537,166.619491 C594,66.8731637 630,15.6666667 645,13 C667.5,9 667.5,-6.5 680.5,3.11949108 C693.5,12.7389822 680.5,24.5 680.5,37.5 C680.5,46.1666667 640.666667,94.8333333 561,183.5 L537,166.619491 Z"
      },
      spoon2: {
        fill: "#B6B6B6",
        d: "M550,175.5 C634.333333,63.5 679.166667,7.5 684.5,7.5 C692.5,7.5 690,31 693,49 C695,61 651.666667,106.666667 563,186 L550,175.5 Z",
      },
      submitter: "Shannon",
      title: "Gumbo",
      paragraphs: ["A Christmas Eve staple in our family, nothing warms the belly and soul like a shrimp and sausage gumbo!", "It's all about the roux, but charred andouille, okra, and shimp also star."],
      link: "https://www.allrecipes.com/recipe/216888/good-new-orleans-creole-gumbo/",
      toppings1: soup7_toppings2,
      toppings2: soup7_toppings1,
    },
    // Kelsey's turkey soup
    { 
      bowl_outer: {
        fill: "#BA6547",
        r: 357
      },
      bowl_inner: {
        fill: "#7C4230",
        r: 335
      },
      broth: {
        fill: "#E9B25B",
        r: 309
      },
      spoon1: {
        fill: "#B4D3D6",
        d: "M557.418443,213.433239 C635.656772,85.3704216 680.275937,19.3390128 691.275937,15.3390128 C707.775937,9.33901278 704.652584,9.92465112 716.54087,16.3552173 C728.429156,22.7857835 714.69684,36.9386887 714.69684,49.9386887 C714.69684,58.6053554 670.770708,119.603539 582.918443,232.933239 L557.418443,213.433239 Z"
      },
      spoon2: {
        fill: "#8CAAAD",
        d: "M569.312095,225.770434 C658.389634,85.6001865 705.59507,15.5150626 710.928403,15.5150626 C718.928403,15.5150626 722.616249,24.6033909 722.616249,37.6033909 C722.616249,46.2700576 675.939847,111.736606 582.587043,234.003038 L569.312095,225.770434 Z",
      },
      submitter: "Kelsey",
      title: "Thanksgiving Turkey Soup",
      paragraphs: ["The day after thanksgiving we always make soup. Just take your turkey carcass, put it in a pot, fill it with water, let it simmer the entire day (or however long you’d like) while skimming off fat, and add salt to taste.", "You can eat it with whatever you like, but we like to throw in some somen noodles, green onion, leftover turkey, and sometimes lao gan ma."],
      toppings1: soup8_toppings2,
      toppings2: soup8_toppings1,
    },
  ]

  const sceneWidth = 600;
  const tileWidth = 350;
</script>

<Section {bgColor}>
  <div class="sticky">
    <SoupBowl width="600px" height="750px" {...soups[index]} />
    <div class="offset" style={`width:${tileWidth}px;`} />
  </div>
  <div class="text mobile-offset">
    <div class="offset" style={`width:${sceneWidth}px;`} />
    <Scrolly bind:value={index}>
      {#each soups as soup, i}
        <Tile style={`width:${tileWidth}px;`}>
          <span class="count">{i + 1} / {soups.length}</span>
          <h2 class="tile-header">{soup.title}</h2>
          <h4>From {soup.submitter}</h4>
          {#each soup.paragraphs as line}
            <p>{line}</p>
          {/each}
          {#if soup.link}
            <p>
              <a href={soup.link} style="font-style:italic;" target="_blank" rel="noopener noreferrer">Recipe link</a>
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
  .tile-header {
    margin: 0px;
    margin-top: 10px;
  }
  h4 {
    margin: 10px 0px;
    margin-bottom: 20px;
    font-weight: 400;
    color: #343434;
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
  .count {
    position: absolute;
    right: 10px;
    top: 10px;
    font-size: 0.8rem;
    color: #8f8f8f;
  }

  a {
    color: rgb(21, 89, 21);
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