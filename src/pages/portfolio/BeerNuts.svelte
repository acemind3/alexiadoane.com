<script>
  import AceLink from "../../lib/AceLink.svelte";
  import Footer from "../../lib/Footer.svelte";
  import Gallery from "../../lib/Gallery.svelte";
  import HeroImage from "../../lib/HeroImage.svelte";
  import HeroTitle from "../../lib/HeroTitle.svelte";
  import Navbar from "../../lib/Navbar.svelte";
  import TwoColumnContentBlock from "../../lib/TwoColumnContentBlock.svelte";

  const skills = [
    "Art direction",
    "Photoshoot coordination",
    "Collaboration with Video and Photo teams",
    "Website design",
    "Collaboration with developers",
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
      <li>developing prop and shot lists</li>
      <li>casting, scheduling, and organizing models</li>
      <li>scouting, contacting, and scheduling locations</li>
      <li>
        organizing and communicating with the videographer and photographer
      </li>
      <li>art directing</li>
    </ul>

    <p>
      I later designed the new Beer Nuts shopify site using the imagery captured
      during the photo/videoshoot. The website phase consisted of developing a
      wireframe for the client, and eventually moved into a 3 round design
      phase. Once designs were approved, I collaborated with developers to
      implement the final website.
    </p>

    <p class="designed-at">
      Work Designed at
      <AceLink href="https://surface51.com/">Surface 51</AceLink>
    </p>
  </div>
</TwoColumnContentBlock>
<Gallery
  images={[
    {
      src: "/beernuts-camping.jpg",
      altText: "placeholder",
      columnWidth: 2,
    },
    {
      src: "/beernuts-camping.jpg",
      altText: "placeholder",
      columnWidth: 1,
    },
    {
      src: "/beernuts-camping.jpg",
      altText: "placeholder",
      columnWidth: 1,
    },
    {
      src: "/beernuts-feature.jpg",
      altText: "placeholder",
      columnWidth: 1,
    },
    {
      src: "/placeholder-img.jpg",
      altText: "placeholder",
      columnWidth: 1,
    },
    {
      src: "/beernuts-camping.jpg",
      altText: "placeholder",
      columnWidth: 2,
    },
    {
      src: "/placeholder-img.jpg",
      altText: "placeholder",
      columnWidth: 1,
    },
  ]}
/>

<Footer />

<style lang="scss">
  @import "../../style/global.scss";

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
