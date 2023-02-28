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
    "Logo design",
    "Brand identity",
    "Vehicle graphics",
    "Environemental graphics",
    "Collateral",
    "Signage",
  ];
</script>

<Navbar />
<div class="hero-container">
  <HeroImage
    imageUrl="/tag-feature.jpg"
    spacing="between"
    imagePosition="overlap"
  >
    <HeroTitle
      websiteUrl="https://www.atkinsgroup.com/"
      titleText="The Atkins Group"
      tags={["Brand Identity"]}
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
      At Surface 51, I designed a new identity for The Atkins Group. This
      consisted of creating a new logo along with a new look and feel. Within
      the TAG brand, there are 5 areas of expertise that needed to be taken
      under consideration. Each needed to have its own identifier, so in
      addition to choosing the core TAG colors of black and red, 4 additional
      colors were chosen to represent these areas. Only 4 colors were chosen
      because TAG decided to use their core red color for one of their expertise
      areas.
    </p>

    <p class="designed-at">
      Work Designed at
      <AceLink href="https://surface51.com/">Surface 51</AceLink>
    </p>
  </div>
</TwoColumnContentBlock>

<GridGallery
  images={[
    {
      src: "/tag_collateral.jpg",
      altText:
        "image of letterhead, envelope and businss cards with TAG branding",
      columnWidth: 1,
    },
    {
      src: "/tag-farm-sign.jpg",
      altText:
        "three friend sitting in chairs around campsite with beernuts cooler",
      columnWidth: 1,
    },
    {
      src: "/tag-front-door.jpg",
      altText: "two people canoeing down river with beernuts tshirts on",
      columnWidth: 1,
    },
    {
      src: "/tag-truck.jpg",
      altText: "beernuts snack on bar counter with beer",
      columnWidth: 1,
    },

    {
      src: "/tag-billboards.jpg",
      altText: "close up of hand grabing peanut from beernuts container",
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
