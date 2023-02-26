<script lang="ts">
  export let imageUrl: string;
  export let spacing: "around" | "between" = "around";
  export let responsiveBackgroundIsWhite: boolean = true;
</script>

<div
  class="hero hero__spacing--{spacing}"
  class:hero__responsive-color={responsiveBackgroundIsWhite}
>
  <img class="hero-image" src={imageUrl} alt="hero" />
  <slot />
</div>

<style lang="scss">
  @import "../style/global.scss";

  .hero-image {
    max-width: 55%;
    clip-path: polygon(100% 0, 100% 41%, 54% 100%, 0 100%, 0 0);

    @include mediumBreakpoint {
      height: auto;
      max-width: 80%;
      width: 80%;
      min-height: unset;
    }
    @include smallBreakpoint {
      width: 100%;
      max-width: 100%;
    }

    /*
    & .overlay {
      background-color: $charcoal;
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
    display: flex;
    justify-content: space-around;
    align-items: flex-start;
    gap: 64px;

    &__spacing--around {
      justify-content: space-around;
    }
    &__spacing--between {
      justify-content: space-between;
    }
    @include mediumBreakpoint {
      flex-direction: column;
    }
    &__responsive-color {
      @include mediumBreakpoint {
        background-color: $almost-white;
      }
    }
  }
</style>
