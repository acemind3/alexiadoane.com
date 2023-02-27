<script lang="ts">
  import SectionTitle from "../lib/SectionTitle.svelte";
  import { Link } from "svelte-routing";

  interface ImageLinkPair {
    src: string;
    link: string;
    isExternalLink?: boolean;
  }

  const imageLocations: ImageLinkPair[] = [
    {
      src: "beernuts_thumbnail.jpg",
      link: "/beernuts",
    },
    {
      src: "iecam-thumbnail.png",
      link: "https://pixotech.com/work/illinois-early-childhood-asset-map-website/",
      isExternalLink: true,
    },
    {
      src: "TAG_thumbnail.jpg",
      link: "/tag",
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
        <a
          class="gallery__item"
          href={image.link}
          target={image.isExternalLink ? "_blank" : "_self"}
        >
          {#if image.isExternalLink}
            <div class="gallery__img_external-link-wrapper">
              <svg
                width="16"
                height="16"
                viewBox="0 0 16 16"
                fill="#3A5DDC"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  fill-rule="evenodd"
                  clip-rule="evenodd"
                  d="M12 8.80001C12 8.35822 12.3582 8.00001 12.8 8.00001C13.2418 8.00001 13.6 8.35822 13.6 8.80001V13.6C13.6 14.9255 12.5255 16 11.2 16H2.4C1.07447 16 0 14.9255 0 13.6V4.8C0 3.47447 1.07447 2.4 2.4 2.4H7.20001C7.64179 2.4 8.00001 2.75821 8.00001 3.2C8.00001 3.64179 7.64179 4 7.20001 4H2.4C1.95821 4 1.6 4.35822 1.6 4.8V13.6C1.6 14.0418 1.95821 14.4 2.4 14.4H11.2C11.6418 14.4 12 14.0418 12 13.6V8.80001Z"
                  fill="#3A5DDC"
                />
                <path
                  fill-rule="evenodd"
                  clip-rule="evenodd"
                  d="M14.3996 1.6H10.3996C9.95782 1.6 9.59961 1.24179 9.59961 0.800001C9.59961 0.358213 9.95782 0 10.3996 0H15.1996C15.6414 0 15.9996 0.358213 15.9996 0.800001V5.6C15.9996 6.04179 15.6414 6.4 15.1996 6.4C14.7578 6.4 14.3996 6.04179 14.3996 5.6V1.6Z"
                  fill="#3A5DDC"
                />
                <path
                  fill-rule="evenodd"
                  clip-rule="evenodd"
                  d="M6.96601 10.1659C6.65351 10.4783 6.14709 10.4783 5.83458 10.1659C5.52226 9.85345 5.52226 9.34702 5.83458 9.03451L14.6346 0.234507C14.9471 -0.077813 15.4535 -0.077813 15.766 0.234507C16.0783 0.547006 16.0783 1.05343 15.766 1.36594L6.96601 10.1659Z"
                  fill="#3A5DDC"
                />
              </svg>
            </div>
          {/if}
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

    @include smallBreakpoint {
      padding: 80px 0px;
    }

    &__item {
      position: relative;
      transition: all 0.2s ease-in;
      display: inline-block;
      overflow: hidden;
      width: 320px;
      height: 267px;

      &:hover {
        transform: translateX(2px) translatey(2px);

        img {
          transform: scale(1.1);
        }
      }
    }

    &__img {
      vertical-align: middle;
      width: 100%;
      height: 100%;
      transition: transform 0.2s ease-in;

      &_external-link-wrapper {
        background-color: $off-white;
        width: 24px;
        height: 24px;
        padding: 12px;
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;

        position: absolute;
        top: 12px;
        right: 12px;
        z-index: 3;
        svg path {
          fill: $thick-blue;
        }
      }
    }
  }
</style>
