<script lang="ts">
  type textFormatType = "small" | "medium";

  export let textFormat: textFormatType = "small";
</script>

<div class="section-title">
  <div class="section-title__background" />
  <h2 class="section-title__text section-title__text--{textFormat}">
    <slot />
  </h2>
</div>

<style lang="scss">
  @import "../style/global.scss";

  .section-title {
    position: relative;
    width: fit-content;
    padding-left: 14px;
    padding-right: 12px;
    &__background {
      position: absolute;
      width: 100%;
      height: 100%;
      top: 6px;
      left: 0;
      background-color: $tag-color;
      clip-path: polygon(10% 0, 100% 0%, 87% 100%, 0% 100%);
      z-index: 0;
    }
    &__text {
      font-family: $primary-font;
      font-weight: 700;
      z-index: 1;
      position: relative;

      &--small {
        letter-spacing: 2px;
        text-transform: uppercase;
        font-size: 16px;
      }
      &--medium {
        font-size: 40px;
        font-weight: 200;

        @include mediumBreakpoint {
          font-size: 24px;
        }
      }
    }
  }
</style>
