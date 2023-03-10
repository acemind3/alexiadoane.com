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
    "brand identity",
    "collaborate with copy writers and brand strategists",
    "coordinate with vendors",
  ];
</script>

<Navbar />
<div class="hero-container">
  <HeroImage
    imageUrl="/martens-center-feature.webp"
    spacing="between"
    imagePosition="overlap"
  >
    <HeroTitle
      titleText="Martens Center brand identity for donation campaign"
      tags={["Brand identity"]}
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
      The Martens Center is a recreation facility built in an underserved
      neighborhood in Champaign, IL. The center is home to the Don Moyer Boys
      and Girls Club and features a gym, indoor track, kitchen, fitness center,
      multipurpose rooms, and media center.
    </p>
    <p>
      With this center, the Champaign Park District aimed to offer a
      state-of-the-art facility with lower-cost memberships. I developed the
      core identity and materials for the fundraising campaign when the building
      was first looking for donors. I created the look and feel, overview
      booklet, and folder for the new building space.
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
      src: "/martens-center-website.webp",
      altText: "image of website mockup",
      columnWidth: 2,
    },
    {
      src: "/martens-center-booklet.webp",
      altText: "image of booklet",
      columnWidth: 2,
    },
    {
      src: "/martens-center-folder.webp",
      altText: "image of folder",
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

  .aptech-gif {
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
