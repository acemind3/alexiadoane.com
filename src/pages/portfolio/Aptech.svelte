<script>
  import AceLink from "../../lib/AceLink.svelte";
  import Footer from "../../lib/Footer.svelte";
  import HeroImage from "../../lib/HeroImage.svelte";
  import HeroTitle from "../../lib/HeroTitle.svelte";
  import Navbar from "../../lib/Navbar.svelte";
  import TwoColumnContentBlock from "../../lib/TwoColumnContentBlock.svelte";
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
    imageUrl="/aptech-feature.webp"
    spacing="between"
    imagePosition="overlap"
  >
    <HeroTitle
      titleText="Advanced filtering for pavement tool"
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
      I worked with a pavement company to enhance their application for
      monitoring airport runways. The existing tool needed a way for users to
      find pavement distresses faster and plan their repair budgets accordingly.
      I worked on a development team to create an advanced filtering feature to
      offer users greater control when searching for certain distresses.
    </p>
    <p>
      The feature we designed allows a user to filter pavement by condition,
      surface type, distress type, age, and use. Once filters are applied, a
      user can see data for their selected types in a table view, as well as a
      map view that shows the location of the distressed pavement meeting their
      specific filtering conditions at the airport.
    </p>

    <p class="designed-at">
      Work Designed at
      <AceLink href="https://pixotech.com/">Pixo</AceLink>
    </p>
  </div>
</TwoColumnContentBlock>

<div class="gif-container">
  <video playsinline autoplay muted loop class="aptech-gif">
    <source src="/aptech-filters-vp9-chrome.webm" type="video/webm" />
    <source src="/aptech-filters-hevc-safari.mp4" type="video/mp4" />
  </video>
</div>

<GridGallery
  images={[
    {
      src: "/aptech-condition.webp",
      altText:
        "wireframe screenshot and screenshot of working software of condition tab in the pavement tool filter section",
      columnWidth: 2,
    },
    {
      src: "/aptech-distress.webp",
      altText:
        "wireframe screenshot and screenshot of working software of distress tab in the pavement tool filter section",
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
