<script>
  import AceLink from "../../lib/AceLink.svelte";
  import Footer from "../../lib/Footer.svelte";
  import Gallery from "../../lib/Gallery.svelte";
  import HeroImage from "../../lib/HeroImage.svelte";
  import HeroTitle from "../../lib/HeroTitle.svelte";
  import Navbar from "../../lib/Navbar.svelte";
  import TwoColumnContentBlock from "../../lib/TwoColumnContentBlock.svelte";
  import GridGallery from "../../lib/GridGallery.svelte";
  import SectionTitle from "../../lib/SectionTitle.svelte";
  import OneColumnContentBlock from "../../lib/OneColumnContentBlock.svelte";

  const skills = [
    "website design",
    "collaboration with content strategists",
    "collaboaration with developers",
  ];
</script>

<Navbar />
<div class="hero-container">
  <HeroImage
    imageUrl="/iecam-feature.webp"
    spacing="between"
    imagePosition="overlap"
  >
    <HeroTitle
      websiteUrl="https://iecam.illinois.edu/"
      titleText="IECAM website"
      tags={["Website Design"]}
    />
  </HeroImage>
</div>
<div class="iecam-summary-container">
  <TwoColumnContentBlock
    leftSectionTitle="Summary"
    rightSectionTitle="Skill Sets"
    rightSectionItems={skills}
    leftSectionFontSize="small"
    marginTopSize="medium"
  >
    <div class="paragraph-spacer" slot="left">
      <p>
        The Illinois Early Childhood Asset Map (IECAM) collects and analyzes
        data related to early childhood services from various state agencies and
        makes the data accessible to the public. IECAM was looking for a full
        site redesign.
      </p>

      <p class="designed-at">
        Work Designed at
        <AceLink href="https://pixotech.com/">Pixo</AceLink>
      </p>
    </div>
  </TwoColumnContentBlock>
</div>

<div class="detail-description-container">
  <div class="gif-container">
    <video playsinline autoplay muted loop class="iecam-gif">
      <source src="/iecam-screen-vp9-chrome.webm" type="video/webm" />
      <source src="/iecam-screen-hevc-safari.mp4" type="video/mp4" />
    </video>
  </div>
  <!-- Prcoess step 1 -->
  <OneColumnContentBlock
    leftSectionTitle="Process"
    leftSectionFontSize="small"
    marginTopSize="small"
    contentUsedAsSummaryOrBody="body"
  >
    <div class="paragraph-spacer" slot="left">
      <h3 class="process-header process-header__first">Design gut test</h3>
      <p>
        I began by doing an activity with the client called a design gut check.
        This consists of pulling screenshots of various websites that vary in
        looks such as layout, imagery, iconography, etc. During the worksession,
        I gave the client 20 seconds to look at one screenshot of one website
        and rank it on a scale of 1-5 with 1 having a negative reaction and 5
        being extremely positive. In the end, we discussed which websites they
        were drawn to and why. The purpose of the test was to identify visual
        likes and dislikes, and to create a shared language to talk about
        design.
      </p>
    </div>
  </OneColumnContentBlock>
  <div class="gut-test-img">
    <GridGallery
      images={[
        {
          src: "/iecam_gut-test.webp",
          altText:
            "screenshots of various website examples taken from the gut test side by side with the client score sheet.",
          columnWidth: 2,
        },
      ]}
    />
  </div>
  <!-- Process Step 2 -->
  <div class="body-paragraph-container">
    <div class="body-paragraph-container__content">
      <h3 class="process-header">Design palettes</h3>
      <p class="body-content">
        I took my findings from the design gut test as well as any relevant
        information our content strategist discovered during their discovery
        phase, and begin exploring design directions using design palettes.
        These palettes show just enough information for the client to understand
        how type styles, button styles, color schemes, design elements, and
        image styles come together to create their new look. For this client, I
        made 5 variations, and we discussed and refined until we finalized one.
      </p>
    </div>
  </div>
  <GridGallery
    images={[
      {
        src: "/iecam_design-palette.webp",
        altText:
          "screenshots of design palettes shown with the final chosen one",
        columnWidth: 2,
      },
    ]}
  />

  <!-- Process Step 3 -->
  <div class="body-paragraph-container">
    <div class="body-paragraph-container__content">
      <h3 class="process-header">Defining styles and components</h3>
      <p class="body-content">
        With the approved design palette, I began on desinging the color
        palette, type styles and buttons styles. These basic ideas then were
        used in the creation of our reusable responsive basic component blocks
        that would be used throughout the website.
      </p>
    </div>
  </div>

  <GridGallery
    images={[
      {
        src: "/iecam-styles.webp",
        altText:
          "screenshots of type styles, button styles, and color palettes",
        columnWidth: 1,
      },
      {
        src: "/iecam-basic-components.webp",
        altText: "screenshots responsive reusable components",
        columnWidth: 1,
      },
    ]}
  />

  <!-- Process Step 4 -->
  <div class="body-paragraph-container">
    <div class="body-paragraph-container__content">
      <h3 class="process-header">Designing homepage and basic pages</h3>
      <p class="body-content">
        With consistant checkins and review with the client throughout the
        system we had to created to design the homepage and other unique pages.
        The content strategists worked with the client to figure out approrpiate
        content and made quick wireframes. I used those wireframes to design the
        content types.
      </p>
    </div>
  </div>

  <GridGallery
    images={[
      {
        src: "/iecam-homepage.webp",
        altText: "screenshots of homepage",
        columnWidth: 1,
      },
      {
        src: "/iecam-other-pages.webp",
        altText: "screenshots of other pages",
        columnWidth: 1,
      },
    ]}
  />
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

  .detail-description-container {
    background-image: $background-secondary-gradient;
  }

  .gut-test-img {
    margin-top: 80px;
  }

  .process-header {
    font-family: $primary-font;
    font-weight: 100;
    font-size: 32px;

    &__first {
      margin-top: 20px;
    }
  }

  .body-paragraph-container {
    margin: 0 auto;
    max-width: 72rem;
    position: relative;
    z-index: 1;
    padding: 32px 0px 32px 0px;

    &__content {
      display: grid;
      grid-template-columns: 1fr;
      padding: 96px;
      font-family: $primary-font;
      font-size: 24px;
      line-height: 40px;
      font-weight: 200;

      @include smallBreakpoint {
        font-size: 24px;
        line-height: 40px;
        padding-left: 16px;
      }
    }

    .body-content {
      margin-top: 24px;
    }
  }

  .gif-container {
    margin: auto;
    max-width: 115rem;
  }

  .iecam-gif {
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
