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
    "Collaboration with developers and content strategists",
    "vendor coordination",
  ];
</script>

<Navbar />
<div class="hero-container">
  <HeroImage
    imageUrl="/beernuts-feature.jpg"
    spacing="between"
    imagePosition="overlap"
  >
    <HeroTitle
      websiteUrl="https://google.com"
      titleText="Beer Nuts"
      tags={["Website Design", "Photoshoot"]}
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
      Beer Nuts is a national brand snack company based out of Bloomington, IL.
      I planned and art directed a 3 day photo/videoshoot.
    </p>

    <p>This included:</p>
    <ul class="bulleted-list">
      <li>developing a prop and shot list</li>
      <li>casting, scheduling, and organizing models</li>
      <li>scouting, contacting, and scheduling locations</li>
      <li>
        organizing and communicating with the videographer and photographer
      </li>
      <li>art directing</li>
    </ul>

    <p>
      A new website was later designed and developed using the imagery captured
      during the photo/videoshoot. The website phase consisted of developing a
      wireframe, design mockups and collaboration with developers to implement.
    </p>

    <p class="designed-at">
      Work Designed at
      <AceLink href="https://surface51.com/">Surface 51</AceLink>
    </p>
  </div>
</TwoColumnContentBlock>
<!-- <div class="video-container">
    <video class="beernuts-video" autoplay loop playsinline>
      <source src="/beernuts-website.webm" type="video/webm" />
    </video>
  </div> -->

<div class="gif-container">
  <img class="beernuts-gif" src="/beernuts-website.gif" />
</div>
<GridGallery
  images={[
    {
      src: "/beernuts-family-eating.webp",
      altText: "family eating at picnic table with beernuts snacks",
      columnWidth: 1,
    },
    {
      src: "/beernuts-canoe.webp",
      altText: "two people canoeing down river with beernuts tshirts on",
      columnWidth: 1,
    },
    {
      src: "/beernuts-product.webp",
      altText: "beernuts snack on bar counter with beer",
      columnWidth: 1,
    },
    {
      src: "/beernuts-bar.webp",
      altText: "man sitting at bar with beernuts glass",
      columnWidth: 1,
    },
    {
      src: "/beernuts-boat-peanuts.webp",
      altText: "close up of hand grabing peanut from beernuts container",
      columnWidth: 1,
    },
    {
      src: "/beernuts-camping.webp",
      altText:
        "three friend sitting in chairs around campsite with beernuts cooler",
      columnWidth: 1,
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

  .beernuts-gif {
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
