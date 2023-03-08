<script>
  import AceLink from "../../lib/AceLink.svelte";
  import Footer from "../../lib/Footer.svelte";
  import Gallery from "../../lib/Gallery.svelte";
  import HeroImage from "../../lib/HeroImage.svelte";
  import HeroTitle from "../../lib/HeroTitle.svelte";
  import Navbar from "../../lib/Navbar.svelte";
  import TwoColumnContentBlock from "../../lib/TwoColumnContentBlock.svelte";
  import OneColumnContentBlock from "../../lib/OneColumnContentBlock.svelte";

  import GridGallery from "../../lib/GridGallery.svelte";

  const skills = [
    "facilitating and leading worksessions with client",
    "wireframming",
    "design user interface",
    "collaborating with engineers to design and implement",
  ];
</script>

<Navbar />
<div class="hero-container">
  <HeroImage
    imageUrl="/wednesday-poster-feature.jpg"
    spacing="between"
    imagePosition="overlap"
  >
    <HeroTitle
      titleText="Personal poster projects"
      tags={["Graphic Design", "Poster Design"]}
    />
  </HeroImage>
</div>
<OneColumnContentBlock
  leftSectionTitle="Summary"
  leftSectionFontSize="small"
  marginTopSize="medium"
>
  <div class="paragraph-spacer" slot="left">
    <p>
      I wanted to include some personal projects I've done. Whenenver I get
      really inspired by a TV show or movie, I get the urge to create a poster
      for it. I've recently complete works for the TV shows Wednesday, Arcane,
      She-Ra and the Princesses of Power, and RWBY. It's a great opportunity for
      me to flex my creative ideas outside of the workplace. It's a labor of
      love, but I create my posters using vector art inside of Illustrator.
    </p>
  </div>
</OneColumnContentBlock>

<div class="poster-gallery">
  <div class="poster-gallery__wrapper">
    <!-- wednesday -->
    <div class="poster-gallery__block">
      <div class="poster-gallery__title">
        <h3>Wednesday</h3>
      </div>
      <div class="poster-gallery__image">
        <img
          class="wednesday-img"
          src="posters_wednesday_web.png"
          alt="netflix wednesday tv show poster"
        />
      </div>
    </div>
    <!-- Arcane -->
    <div class="poster-gallery__block">
      <div class="poster-gallery__title">
        <h3>Arcane</h3>
      </div>
      <div class="poster-gallery__image">
        <img
          class="arcane-img"
          src="posters_jinx_web.png"
          alt="netflix arcane tv show poster"
        />
      </div>
    </div>
    <!-- She Ra -->
    <div class="poster-gallery__block">
      <div class="poster-gallery__title">
        <h3>She-Ra and the Princesses of Power</h3>
      </div>
      <div class="poster-gallery__image">
        <img
          class="shera-img"
          src="posters-adora.png"
          alt="netflix she-ra and the princesses of power tv show poster for Adora"
        />
        <img
          class="catra-img"
          src="posters-catra.png"
          alt="netflix arcane tv show poster for Catra"
        />
      </div>
    </div>
    <!-- RWBY -->
    <div class="poster-gallery__block">
      <div class="poster-gallery__title">
        <h3>RWBY</h3>
      </div>
      <div class="poster-gallery__image">
        <img
          class="rwby-img"
          src="posters-rwby.jpg"
          alt="RWBY tv show poster"
        />
      </div>
    </div>
  </div>
</div>

<Footer />

<style lang="scss">
  @import "../../style/global.scss";

  .hero-container {
    margin: auto;
    max-width: 115rem;
  }
  .bulleted-list {
    margin-left: 24px;
  }
  .paragraph-spacer {
    display: flex;
    flex-direction: column;
    gap: 24px;
  }

  .designed-at {
    text-transform: uppercase;
    font-weight: 700;
    font-size: 16px;
    letter-spacing: 2px;
  }
  p {
    font-family: $primary-font;
  }

  .poster-gallery {
    margin-top: 100px;
    position: relative;
    z-index: 1;
    padding: 0 16px;

    &__wrapper {
      margin: 0 auto;
      max-width: 72rem;
    }

    @include smallBreakpoint {
      margin-top: 120px;
    }
  }

  .poster-gallery__block {
    margin-bottom: 120px;
    @include smallBreakpoint {
      margin-bottom: 72px;
    }
  }

  .poster-gallery__title {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    font-family: $secondary-font !important;
    font-size: 72px;
    text-align: center;
    @include mediumBreakpoint {
      font-size: 64px;
    }
    @include smallBreakpoint {
      font-size: 32px;
    }
  }

  .poster-gallery__image {
    padding: 40px 60px;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 16px;
    row-gap: 64px;
    @include smallBreakpoint {
      padding: 20px 30px;
      gap: 8px;
    }

    .wednesday-img {
      width: 50%;
      height: auto;
      min-width: 275px;
    }

    .arcane-img {
      width: 60%;
      height: auto;
      min-width: 275px;
    }
    .shera-img {
      width: 45%;
      height: auto;
      min-width: 275px;
    }
    .catra-img {
      width: 45%;
      height: auto;
      min-width: 275px;
    }
    .rwby-img {
      width: 60%;
      height: auto;
      min-width: 275px;
    }
  }
</style>
