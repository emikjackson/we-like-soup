<script>
  import SoupScroller from './SoupScroller.svelte';
  import SpoonHero from './SpoonHero.svelte';
  import lights from '$lib/assets/lights.svg';
  import logo from '$lib/assets/ja-logo-horizontal.svg';
</script>

<!-- Decorative veggie string lights -->
<div class="top-lights">
  <img src={lights} alt="" />
</div>

<!-- Intro section -->
<div class="wrapper">

  <h2>'Tis the season of</h2>
  <h1>Soup</h1>

  <!-- Shape-shifting spoon hero-image -->
  <SpoonHero />

  <h3>Some soup inspiration from the January Advisors team</h3>

  <div class="text">
    <p>Perhaps your winter has been similar to ours - getting chillier and interrupted by the occasional illness. A soothing comfort for both cold weather and cold-occupying heads, no food provides that deep-warmth-inside-body feeling quite like soup. With so many ways to ladle out a bowl, soup is also a perfect dish to share with friends and family.</p>
    <p>Here are some of the favorite soups we've had the pleasure of making or consuming this season. We hope they inspire you to enjoy a soup soon!</p>
  </div>
</div>

<!-- Soup scrolling section, displaying each team member's animated soup & related text -->
<SoupScroller />

<!-- Closing section -->
<div class="wrapper">
  <p>That's it! Those were all of our soups.</p>
  <p style="margin-top:0px;">Did our ideas delight? Or make you doubt?</p>
  <p style="margin-top:0px;">We hope you are inspired to try a soup of your own. Happy souping! :)</p>

  <div class="logo">
    <a href="https://www.januaryadvisors.com/" target="_blank" rel="noopener noreferrer">
      <img src={logo} alt="January Advisors" />
    </a>
  </div>
</div>

<style>

  .top-lights {
    display: flex;
    width: 100%;
    overflow: hidden;
    justify-content: center;
  }

  .top-lights > img {
    min-width: 100%;
    width: 1000px;
  }

  .text {
    width: 90%;
    max-width: 700px;
    margin-bottom: 30px;
  }

  .text p {
    margin-top: 20px;
    margin-bottom: 20px;
  }

  .wrapper {
    min-height: 70vh;
    padding: 20px;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    position: relative;
  }

  .wrapper > p {
    text-align: center;
  }

  .logo {
    position: absolute;
    bottom: 20px;
    left: 0px;
    width: 100%;
    text-align: center;
  }

  .logo img {
    width: 150px;
    height: 24px;
  }

  h1 {
    font-size: 5rem;
    letter-spacing: 0.4rem;
    margin-top: 0px;
    margin-bottom: 0px;
  }

  h2 {
    margin-bottom: 10px;
  }

  h3 {
    color: rgb(76, 76, 76);
    text-align: center;
    font-style: italic;
  }
</style>