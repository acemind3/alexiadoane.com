<script lang="ts">
  export let imageUrl: string;
  export let spacing: "around" | "between" = "around";
  export let responsiveBackgroundIsWhite: boolean = true;
  export let hasTransparentImage: boolean = false;
  export let imagePosition: "top" | "overlap" = "overlap";
</script>

<div
  class="hero hero__spacing--{spacing}"
  class:hero__responsive-color={responsiveBackgroundIsWhite}
>
  <img
    class="hero-image hero-image__imagePosition--{imagePosition}"
    class:hero-image__transparent-image={hasTransparentImage}
    src={imageUrl}
    alt="hero"
  />
  <slot />
</div>

<style lang="scss">
  @import "../style/global.scss";

  .hero-image {
    clip-path: polygon(100% 0, 100% 41%, 54% 100%, 0 100%, 0 0);
    position: relative;

    &__imagePosition--top {
      top: 0px;
      max-width: 100%;
    }

    &__imagePosition--overlap {
      top: 50px;
      max-width: 95%;
      position: relative;
    }

    &__transparent-image {
      opacity: 0.5;
    }

    @include mediumBreakpoint {
      height: auto;
      max-width: 80%;
      width: 80%;
      min-height: unset;
      top: 0px;
    }
    @include smallBreakpoint {
      width: 100%;
      max-width: 100%;
    }

    /*
    & .overlay {
      background-color: $text-primary;
      position: absolute;
      top: 0;
      left: 0;
      height: 100%;
      width: 100%;
      opacity: 0.65;
      z-index: 0;
    }
    */
  }

  .hero {
    position: relative;
    font-size: 170px;
    display: grid;
    grid-template-columns: 1fr 1fr;

    // display: flex;
    // justify-content: space-around;
    // align-items: flex-start;
    // gap: 64px;

    &__spacing--around {
      justify-content: space-around;
    }
    &__spacing--between {
      justify-content: space-between;
    }
    @include mediumBreakpoint {
      // flex-direction: column;
      // gap: 0px;
      grid-template-columns: 1fr;
    }
    &__responsive-color {
      @include mediumBreakpoint {
        background-color: $background-secondary;
      }
    }
  }
</style>
