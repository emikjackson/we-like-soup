<script>
  import Scrolly from "$lib/components/Scrolly.svelte";
  import CustomBlob from "../../lib/components/graphics/CustomBlob.svelte";
  import HeaderBlock from "./HeaderBlock.svelte";
  import Section from "./Section.svelte";
  import Tile from "./Tile.svelte";

  let stepIndex = 0;
  const bgColor = "#f3f3f3";

  const blobPath1 = "M389,307.5Q388,365,331,375.5Q274,386,203,420Q132,454,79,393Q26,332,60.5,262.5Q95,193,134.5,155.5Q174,118,231,75.5Q288,33,359,66Q430,99,410,174.5Q390,250,389,307.5Z";
  const blobPath2 = "M415,302.5Q376,355,325,369.5Q274,384,202,421Q130,458,131,375.5Q132,293,96,237Q60,181,100,120.5Q140,60,214,46.5Q288,33,331.5,89Q375,145,414.5,197.5Q454,250,415,302.5Z";
  const blobPath3 = "M427.5,312Q398,374,341,408Q284,442,226,417.5Q168,393,114,356Q60,319,43,243.5Q26,168,91,127.5Q156,87,215.5,98.5Q275,110,326.5,126.5Q378,143,417.5,196.5Q457,250,427.5,312Z";
  const blobPath4 = "M395.5,305Q381,360,331,391.5Q281,423,209,434.5Q137,446,97,383Q57,320,61.5,251.5Q66,183,100.5,117Q135,51,208.5,61Q282,71,331,106Q380,141,395,195.5Q410,250,395.5,305Z";
  const blobPath5 = "M405.05478,313.02739Q400.89724,376.05478,346.94862,433.92236Q293,491.78995,220.15867,459.97261Q147.31734,428.15527,133.78542,362.81621Q120.2535,297.47714,77.68153,234.37099Q35.10956,171.26483,105.34246,146.49773Q175.57537,121.73064,230.44522,85.99887Q285.31507,50.26709,353.42123,78.3436Q421.52739,106.4201,415.36985,178.21005Q409.21232,250,405.05478,313.02739Z";

  // Text to show & blob properties for each step
  let blobSteps = [
    { 
      d: blobPath1,
      fill: "blue",
    },
    { 
      d: blobPath2,
      fill: "green",
    },
    { 
      d: blobPath3,
      fill: "pink",
    },
    { 
      d: blobPath4,
      fill: "red",
      style: "filter: blur(0px);",
    },
    { 
      d: blobPath5,
      fill: "purple",
      style: "filter: blur(0px);",
    },
    { 
      d: blobPath1,
      fill: "grey",
    },
  ]

  let textSteps = [
    {
      header: "Hey it's a blob!",
      text: "Pretty neat."
    },
    {
      header: "Can it be green?",
      text: "Pretty neat."
    },
    {
      header: "How about pink?",
      text: "Pretttttty neat."
    },
    {
      header: "Let's make it crisper.",
      text: "Like a fine apple."
    },
    {
      header: "And now purple",
      text: "Perhaps a fine grape?"
    },
    {
      header: "Okay enough of this.",
      text: "Even though it was pretty neat."
    }
  ]
</script>

<HeaderBlock {bgColor}>
  <h1>Sticky Scrolling!</h1>
  <p>An example of sticky scrolling interactions.</p>
</HeaderBlock>

<Section {bgColor}>
  <div class="sticky">
    <div>
      <CustomBlob {...blobSteps[stepIndex]} />
    </div>
  </div>
  <div class="text">
    <Scrolly bind:value={stepIndex}>
      {#each textSteps as {header, text}}
        <Tile>
          <h2>{header}</h2>
          <p>{text}</p>
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
  }
  .text {
    display: flex;
    flex-direction: column;
    align-items: center;
    position: relative;
    z-index: 1;
  }
</style>