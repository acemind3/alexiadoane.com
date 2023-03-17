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
  <div class="gif-container">
    <video playsinline autoplay muted loop class="iecam-gif">
      <source src="/iecam-screen-vp9-chrome.webm" type="video/webm" />
      <source src="/iecam-screen-hevc-safari.mp4" type="video/mp4" />
    </video>
  </div>
  <HeroTitle
    websiteUrl="https://pixotech.com/"
    titleText="IECAM website"
    tags={["Website Design"]}
  />
</div>
<div class="iecam-summary-container">
  <TwoColumnContentBlock
    leftSectionTitle="Summary"
    rightSectionTitle="Skill Sets"
    rightSectionItems={skills}
    leftSectionFontSize="small"
    marginTopSize="small"
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
  <!-- Prcoess step 1 -->
  <OneColumnContentBlock
    leftSectionTitle="Design gut test"
    leftSectionFontSize="small"
    marginTopSize="small"
    contentUsedAsSummaryOrBody="body"
  >
    <div class="paragraph-spacer" slot="left">
      <p>
        I began by doing an activity with the client called a design gut check.
        This consists of pulling screenshots of various websites that vary in
        looks such as layout, imagery, iconography, etc. During the worksession,
        I gave the client 20 seconds to look at one screenshot of one website
        and rank each one. In the end, we discussed which websites they were
        drawn to and why. The purpose of the test was to identify visual likes
        and dislikes, and to create a shared language to talk about design.
      </p>
    </div>
  </OneColumnContentBlock>
  <div class="description-images">
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

  <OneColumnContentBlock
    leftSectionTitle="design palettes"
    leftSectionFontSize="small"
    marginTopSize="small"
    contentUsedAsSummaryOrBody="body"
  >
    <div class="paragraph-spacer" slot="left">
      <p>
        I took my findings from the design gut test as well as any relevant
        information discovered by our content strategist during their discovery
        phase, and begin exploring design directions using design palettes.
        These palettes show just enough information for the client to understand
        how type styles, button styles, color schemes, design elements, and
        image styles come together to create their new look. For this client, I
        made 5 variations, and we discussed and refined until we finalized one.
      </p>
    </div>
  </OneColumnContentBlock>
  <div class="description-images">
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
  </div>

  <!-- Process Step 3 -->
  <OneColumnContentBlock
    leftSectionTitle="Defining styles and components"
    leftSectionFontSize="small"
    marginTopSize="small"
    contentUsedAsSummaryOrBody="body"
  >
    <div class="paragraph-spacer" slot="left">
      <p>
        With the approved design palette, I began on defining the colors, type
        styles and buttons styles. These basic ideas were used in the creation
        of our reusable responsive basic component blocks that would be used
        throughout the website.
      </p>
    </div>
  </OneColumnContentBlock>

  <div class="description-images">
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
  </div>

  <!-- Process Step 4 -->
  <OneColumnContentBlock
    leftSectionTitle="Designing homepage and basic pages"
    leftSectionFontSize="small"
    marginTopSize="small"
    contentUsedAsSummaryOrBody="body"
  >
    <div class="paragraph-spacer" slot="left">
      <p>
        With consistant checkins and reviews with the client, we designed the
        homepage and other unique pages using the system we designed. The
        content strategists worked with the client to figure out approrpiate
        content and made quick wireframes. I used those wireframes to design the
        content types.
      </p>
    </div>
  </OneColumnContentBlock>

  <div class="description-images">
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
</div>

<Footer />

<style lang="scss">
  @import "../../style/global.scss";

  .detail-description-container {
    background-image: $background-secondary-gradient;
    padding-top: 200px;

    @include smallBreakpoint {
      padding-top: 64px;
      text-align: center;
      font-size: 20px;
      line-height: 24px;
    }
  }

  .description-images {
    margin-top: 80px;
    margin-bottom: 125px;

    @include smallBreakpoint {
      margin-top: 24px;
      margin-bottom: 64px;
    }
  }

  .gif-container {
    margin: auto;
    max-width: 115rem;
    z-index: 1;

    @include mediumBreakpoint {
      background-color: $background-secondary;
    }
  }

  .iecam-gif {
    width: 120%;
    height: auto;

    @include mediumBreakpoint {
      width: 100%;
    }
  }

  .hero-container {
    margin: auto;
    max-width: 115rem;
    display: grid;
    grid-template-columns: 1fr 1fr;

    @include mediumBreakpoint {
      grid-template-columns: 1fr;
    }
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
