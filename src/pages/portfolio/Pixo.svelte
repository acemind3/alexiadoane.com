<script>
  import AceLink from "../../lib/AceLink.svelte";
  import Footer from "../../lib/Footer.svelte";
  import Gallery from "../../lib/Gallery.svelte";
  import HeroImage from "../../lib/HeroImage.svelte";
  import HeroTitle from "../../lib/HeroTitle.svelte";
  import Navbar from "../../lib/Navbar.svelte";
  import TwoColumnContentBlock from "../../lib/TwoColumnContentBlock.svelte";
  import GridGallery from "../../lib/GridGallery.svelte";

  const skills = [
    "logo design",
    "brand identity",
    "website design",
    "print design",
    "animation",
    "collaboration with developers and content strategists",
    "vendor coordination",
  ];
</script>

<Navbar />
<div class="hero-container">
  <HeroImage
    imageUrl="/pixo-logo.gif"
    spacing="between"
    imagePosition="overlap"
  >
    <HeroTitle
      websiteUrl="https://pixotech.com/"
      titleText="Pixo brand identity & website"
      tags={["Brand Identity", "Website Design"]}
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
      While at Pixo, I played an integral role in rebranding and designing new
      marketing materials for the company. My team facilitated work sessions
      with stakeholders to develop a new visual identity and messaging, and we
      developed a brand identity guide and implemented a new website as part of
      this internal project.
    </p>

    <p class="designed-at">
      Work Designed at
      <AceLink href="https://pixotech.com/">Pixo</AceLink>
    </p>
  </div>
</TwoColumnContentBlock>

<!-- <div class="gif-container">
  <img
    class="pixo-gif"
    src="/pixo-website-scroll.gif"
    alt="image of computer scrolling through a page on the pixo website."
  />
</div> -->

<div class="gif-container">
  <video playsinline autoplay muted loop class="pixo-gif">
    <source src="/pixo-website-scroll-vp9-chrome.webm" type="video/webm" />
    <source src="/pixo-website-scroll-hevc-safari.mp4" type="video/mp4" />

  </video>
</div>
<GridGallery
  images={[
    {
      src: "/pixo-brand-guide.webp",
      altText: "screengrabs of various pages from the pixo brand guide",
      columnWidth: 2,
    },
    {
      src: "/pixo-brochures.webp",
      altText: "images of a brochure depicting various pixo services",
      columnWidth: 2,
    },
  ]}
/>

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

  .pixo-gif {
    width: 100%;
    height: auto;
  }

  .hero-container {
    margin: auto;
    max-width: 115rem;
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
