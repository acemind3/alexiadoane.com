<script>
  import AceLink from "../../lib/AceLink.svelte";
  import Footer from "../../lib/Footer.svelte";
  import HeroImage from "../../lib/HeroImage.svelte";
  import HeroTitle from "../../lib/HeroTitle.svelte";
  import Navbar from "../../lib/Navbar.svelte";
  import TwoColumnContentBlock from "../../lib/TwoColumnContentBlock.svelte";
  import GridGallery from "../../lib/GridGallery.svelte";

  const skills = [
    "art direction",
    "photoshoot coordination",
    "collaboration with video and photo teams",
    "website design",
    "collaboration with developers",
  ];
</script>

<Navbar />
<div class="hero-container">
  <HeroImage
    imageUrl="/beernuts-feature.webp"
    spacing="between"
    imagePosition="overlap"
  >
    <HeroTitle
      titleText="Beer Nuts photoshoot & website"
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
      Beer Nuts is a national snack company based in Bloomington, IL. I planned
      and art-directed a three-day photo and video shoot for marketing materials
      and a new website.
    </p>

    <p>This process included:</p>
    <ul class="bulleted-list">
      <li>developing a prop and shot list</li>
      <li>casting, scheduling, and organizing models</li>
      <li>scouting, contacting, and scheduling locations</li>
      <li>
        organizing and communicating with the videographer and photographer
      </li>
      <li>art directing on location</li>
    </ul>

    <p>
      I then designed a new website using images and video captured during the
      shoot. The website phase consisted of developing a wireframe, designing
      mockups, and collaborating with developers to implement a website that
      shows off the product and speaks to their target customers.
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
  <video playsinline autoplay muted loop class="beernuts-gif">
    <source src="/beernuts-website-vp9-chrome.webm" type="video/webm" />
    <source src="/beernuts-website-hevc-safari.mp4" type="video/mp4" />
  </video>
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
