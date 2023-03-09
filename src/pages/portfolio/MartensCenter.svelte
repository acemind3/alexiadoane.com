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
    imageUrl="/martens-center-feature.jpg"
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
      The Martens center is a multi-purpose Champaign Park District facility
      that was built in a lower income neighborhood. The goal was to bring a
      state of the art facility to offer lower-cost memberships. The center is
      also home for the Don Moyer Boys and Girls Club of Champaign and features
      a gym, indoor track, kitchen, fitness center, multi-purpose rooms, and
      media center.
    </p>
    <p>
      I developed the core look and materials for the donation campaign when the
      building was first looking for donors. Surface 51 developed the core
      messaging, and I created the look and feel, overview booklet, and folder
      of the new building space.
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
      src: "/martens-center-website.jpg",
      altText: "image of website mockup",
      columnWidth: 2,
    },
    {
      src: "/martens-center-booklet.jpg",
      altText: "image of booklet",
      columnWidth: 2,
    },
    {
      src: "/martens-center-folder.jpg",
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
