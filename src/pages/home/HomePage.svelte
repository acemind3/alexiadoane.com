<script lang="ts">
  import AboutSection from "../../lib/AboutSection.svelte";
  import Footer from "../../lib/Footer.svelte";
  import HeroImage from "../../lib/HeroImage.svelte";
  import Navbar from "../../lib/Navbar.svelte";
  import Portfolio from "../../lib/Portfolio.svelte";
  import SectionTitle from "../../lib/SectionTitle.svelte";
</script>

<Navbar>
  <a class="nav-jump-link" href="#about">about</a>
  <a class="nav-jump-link" href="#portfolio">portfolio</a>
  <a class="nav-jump-link" href="#contact">contact</a>
</Navbar>
<div class="homepage">
  <div class="homepage-hero-container">
    <HeroImage
      spacing="between"
      imageUrl="/ace-pic.jpg"
      responsiveBackgroundIsWhite={false}
    >
      <img
        class="alex-wordmark"
        src="/alex-wordmark.svg"
        alt="alex doane"
        aria-label="alex doane"
      />
    </HeroImage>
  </div>

  <div class="description-list-container">
    <div class="description-list-content">
      <ul>
        <li>
          <SectionTitle textFormat="medium">graphic designer</SectionTitle>
        </li>
        <li>
          <SectionTitle textFormat="medium">UI/UX designer</SectionTitle>
        </li>
        <li>
          <SectionTitle textFormat="medium">hobby enthusiast</SectionTitle>
        </li>
      </ul>
    </div>
  </div>

  <div class="content__wrapper">
    <div class="triangle" />

    <AboutSection />
    <Portfolio />
    <Footer backgroundType="background" />
  </div>
</div>

<style lang="scss">
  @import "../../style/global.scss";

  @keyframes slideAndFadeIntoView {
    0% {
      opacity: 0;
      transform: translateY(-32px);
    }
    100% {
      opacity: 1;
      transform: translate(0);
    }
  }

  .nav-jump-link {
  }
  .homepage-hero-container {
    margin: 0 auto;
    max-width: 115rem;
  }
  .alex-wordmark {
    width: clamp(200px, 60vw, 800px);
    position: absolute;
    bottom: 0;
    right: 2rem;

    animation: slideAndFadeIntoView 1.5s forwards;
  }

  @keyframes slideUp {
    0% {
      transform: translateY(-50px);
    }
    100% {
      transform: translateY(0);
    }
  }

  .content__wrapper {
    position: relative;
    z-index: 1;
  }

  .triangle {
    background: url("/diamond-bg.svg");
    z-index: 0;
    position: absolute;
    height: 2031px;
    width: 1000vw;
    left: 0;

    @include mediumBreakpoint {
      left: -418px;
      top: 301px;
    }
    @include smallBreakpoint {
      left: -785px;
    }
  }

  .description-list-container {
    margin: 0 auto;
    max-width: 115rem;
  }

  .description-list-content {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    width: 100%;
    margin-top: 64px;

    & ul {
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      flex-grow: 1;
      justify-content: space-evenly;
      font-family: $primary-font;
      font-weight: 200;
      font-size: 2.5rem;
      row-gap: 24px;
      gap: 64px;

      @include smallBreakpoint {
        flex-direction: column;
        align-items: center;
        gap: 24px;
      }
    }

    & li {
      list-style-type: none;
    }
  }
</style>
