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
    "environmental and vehicle graphic design",
    "signage",
    "vendor coordination",
  ];
</script>

<Navbar />
<div class="hero-container">
  <HeroImage
    imageUrl="/tag-feature.webp"
    spacing="between"
    imagePosition="overlap"
  >
    <HeroTitle
      websiteUrl="https://www.atkinsgroup.com/"
      titleText="The Atkins Group brand identity"
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
      The Atkins Group is a land development group based out of Champaign,
      Illinois. I created their new logo and new brand identity to better
      express to the community what they do. Within the TAG brand, there were
      other areas of expertise that needed to be taken into consideration. Each
      needed to have its own identifier, so in addition to choosing the core TAG
      colors of black and red, additional colors were chosen to represent these
      other areas.
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
      src: "/tag_collateral.webp",
      altText:
        "image of letterhead, envelope and businss cards with TAG branding",
      columnWidth: 1,
    },
    {
      src: "/tag-farm-sign.webp",
      altText: "image of farm sign depicting the TAG branding",
      columnWidth: 1,
    },
    {
      src: "/tag-front-door.webp",
      altText:
        "image of the TAG front door with environemental graphics on it showing the TAG branding",
      columnWidth: 1,
    },
    {
      src: "/tag-truck.webp",
      altText:
        "image of a TAG truck with graphics on it showing the TAG branding",
      columnWidth: 1,
    },

    {
      src: "/tag-billboards.webp",
      altText: "mockups of TAG branded billboards",
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
