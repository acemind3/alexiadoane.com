<script lang="ts">
  type GalleryImage = {
    src: string;
    altText: string;
    columnWidth: 1 | 2;
    hoverText?: string;
  };

  export let images: GalleryImage[];
  export let imageSizeConstraints: { height: number; width: number } = null;
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
          style="height:{imageSizeConstraints?.height ??
            'unset'};width:{imageSizeConstraints?.width ?? 'unset'};"
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
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;

    //grid-template-columns: 1fr 1fr;
    gap: $gap-size;
    padding: 0 $gutter-size;

    @include smallBreakpoint {
      padding: 0 $small-gutter-size;
    }

    &__img {
      //max-width: 100vw;
      max-width: calc(100% - $gutter-size);
      height: auto;

      @include smallBreakpoint {
        max-width: calc(100% - $small-gutter-size);
      }

      &-wrapper {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        // width: 100%;
        // height: 100%;

        // &--width-1 {
        //   grid-column: span 1;

        //   img {
        //     max-width: calc(45% - $gap-size - $gutter-size);
        //   }
        // }
        // &--width-2 {
        //   grid-column: span 2;

        //   max-width: calc(100% - $gutter-size);
        // }
      }
    }
  }
</style>
