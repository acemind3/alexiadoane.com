<script>
  import AceLink from "../../lib/AceLink.svelte";
  import Footer from "../../lib/Footer.svelte";
  import HeroImage from "../../lib/HeroImage.svelte";
  import HeroTitle from "../../lib/HeroTitle.svelte";
  import Navbar from "../../lib/Navbar.svelte";
  import TwoColumnContentBlock from "../../lib/TwoColumnContentBlock.svelte";
  import OneColumnContentBlock from "../../lib/TwoColumnContentBlock.svelte";

  import GridGallery from "../../lib/GridGallery.svelte";

  const skills = [
    "UX design",
    "UI design",
    "collaboration with developers and content strategists",
  ];
</script>

<Navbar />
<div class="hero-container">
  <HeroImage
    imageUrl="/interactive-component-feature.webp"
    spacing="between"
    imagePosition="overlap"
  >
    <HeroTitle
      websiteUrl="https://www.precisionplanting.com/"
      titleText="Interactive farm equipment component"
      tags={["UX Design", "UI Design"]}
    />
  </HeroImage>
</div>
<TwoColumnContentBlock
  leftSectionTitle="Summary"
  rightSectionTitle="Skill Sets"
  rightSectionItems={skills}
  leftSectionFontSize="small"
  marginTopSize="medium"
>
  <div class="paragraph-spacer" slot="left">
    <p>
      Precision Planting is an international company that develops products that
      improve planting and harvest operations using smart technology. For the
      company’s website homepage, I designed an interactive component that would
      allow the user to visualize and explore product features. I collaborated
      with a web development team to implement intuitive and accessible
      interactions that perform well on both desktop and mobile.
    </p>

    <p class="designed-at">
      Work Designed at
      <AceLink href="https://pixotech.com/">Pixo</AceLink>
    </p>
  </div>
</TwoColumnContentBlock>
<!-- <div class="video-container">
    <video class="beernuts-video" autoplay loop playsinline>
      <source src="/beernuts-website.webm" type="video/webm" />
    </video>
  </div> -->

<div class="gif-container">
  <video playsinline autoplay muted loop class="interactive-component-gif">
    <source src="/interactive-component-vp9-chrome.webm" type="video/webm" />
    <source src="/interactive-component-hevc-safari.mp4" type="video/mp4" />
  </video>
</div>

<Footer />

<style lang="scss">
  @import "../../style/global.scss";

  // .video-container {
  //   margin: auto;
  //   max-width: 115rem;
  // }

  // .beernuts-video {
  //   width: 100%;
  //   height: auto;
  // }

  .gif-container {
    margin: auto;
    max-width: 115rem;
  }

  .interactive-component-gif {
    width: 100%;
    height: auto;
  }

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
</style>
