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
    "facilitate and lead worksessions with stakeholders",
    "create wireframes and prototypes",
    "design user interface",
  ];
</script>

<Navbar />
<div class="hero-container">
  <HeroImage
    imageUrl="/safer-illinois-feature.webp"
    spacing="between"
    imagePosition="overlap"
  >
    <HeroTitle
      websiteUrl="https://rokwire.org/safer-illinois-app-archive/"
      titleText="Safer Illinois app"
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
      In an effort to keep students, staff, and faculty safe to return to campus
      in the fall of 2020, the University of Illinois developed a new saliva
      test that could rapidly test for Covid 19. The University mandated that
      all students, faculty and staff tested regularly. For this extensive
      testing to work, an app was created to support the process. I was part of
      the team that brainstormed and designed the Safer Illinois app.
    </p>

    <p>The Safer Illinois app:</p>
    <ul class="bulleted-list">
      <li>let students and staff know when and where to get tested</li>
      <li>how often to get tested</li>
      <li>their test results and what to do if they tested positive</li>
      <li>a building access status pass based on their testing result</li>
      <li>offer community health recommendations</li>
      <li>notify users of proximity-based exposures</li>
    </ul>

    <p>
      The app was used during Covid to keep the community safe and healthy,
      while inspring other universities and communities to develop their own
      testing protocols.
    </p>

    <p class="designed-at">
      Work Designed at
      <AceLink href="https://pixotech.com/">Pixo</AceLink>
    </p>
  </div>
</TwoColumnContentBlock>
<GridGallery
  images={[
    {
      src: "/illinois-app-intro.webp",
      altText: "intro screens of the safer illinois app",
      columnWidth: 2,
    },
    {
      src: "/illinois-app-screens.webp",
      altText: "various screens from inside the safer illinois app",
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
