<script lang="ts">
  import SectionTitle from "../lib/SectionTitle.svelte";
  import { Link } from "svelte-routing";

  interface ImageLinkPair {
    src: string;
    link: string;
  }

  const imageLocations: ImageLinkPair[] = [
    {
      src: "beernuts_thumbnail.jpg",
      link: "/beernuts",
    },
    {
      src: "placeholder-img.jpg",
      link: "",
    },
    {
      src: "placeholder-img.jpg",
      link: "",
    },
    {
      src: "placeholder-img.jpg",
      link: "",
    },
    {
      src: "placeholder-img.jpg",
      link: "",
    },
    {
      src: "placeholder-img.jpg",
      link: "",
    },
    {
      src: "placeholder-img.jpg",
      link: "",
    },
    {
      src: "placeholder-img.jpg",
      link: "",
    },
    {
      src: "placeholder-img.jpg",
      link: "",
    },
  ];
</script>

<div id="portfolio" class="portfolio">
  <div class="portfolio-container">
    <div class="galleryTitle">
      <div class="galleryTitle__wrapper">
        <SectionTitle>Portfolio</SectionTitle>
      </div>
    </div>

    <div id="gallery" class="gallery">
      {#each imageLocations as image}
        <a href={image.link}>
          <img class="gallery__img" src={image.src} placeholder="image" />
        </a>
      {/each}
    </div>
  </div>
</div>

<style lang="scss">
  @import "../style/global.scss";

  .portfolio {
    margin-top: 200px;
    position: relative;
    z-index: 1;
    .portfolio-container {
      margin: 0 auto;
      max-width: 115rem;
    }

    @include smallBreakpoint {
      margin-top: 120px;
    }
  }

  .galleryTitle {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
  }

  .gallery {
    padding: 80px 60px;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 16px;

    &__img {
      width: 320px;
      height: 267px;
      transition: all 0.2s ease-in;

      &:hover {
        box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.8);
        transform: translateX(2px) translatey(2px);
      }
    }
  }
</style>
