<script lang="ts">
  type GalleryImage = {
    src: string;
    altText: string;
    columnWidth: 1 | 2;
    hoverText?: string;
  };

  export let images: GalleryImage[];
</script>

<div class="gallery-container">
  <div class="gallery">
    {#each images as image}
      <div
        class="gallery__img-wrapper gallery__img-wrapper--width-{image.columnWidth}"
      >
        <img
          class="gallery__img "
          src={image.src}
          alt={image.altText}
          aria-label={image.altText}
        />
      </div>
    {/each}
  </div>
</div>

<style lang="scss">
  @import "../style/global.scss";
  $gap-size: 30px;
  $gutter-size: 96px;
  $small-gutter-size: 32px;

  .gallery-container {
    margin: 0 auto;
    max-width: 115rem;
  }
  .gallery {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: $gap-size;
    padding: 0 $gutter-size;
    justify-items: center;

    @include smallBreakpoint {
      padding: 0 $small-gutter-size;
      grid-template-columns: 1fr;
    }

    &__img {
      width: 100%;
      height: 100%;
      object-fit: cover;

      &-wrapper {
        display: grid;

        width: 100%;
        height: 100%;
        justify-items: center;

        &--width-1 {
          grid-column: span 1;
        }
        &--width-2 {
          grid-column: span 2;

          @include smallBreakpoint {
            grid-column: span 1;
          }
        }
      }
    }
  }
</style>
