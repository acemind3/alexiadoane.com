<script lang="ts">
  import SectionTitle from "./SectionTitle.svelte";

  export let leftSectionTitle: string;
  export let leftSectionFontSize: "large" | "small" = "large";
  export let marginTopSize: "small" | "medium" | "large" = "large";
  export let contentUsedAsSummaryOrBody: "summary" | "body" = "summary";
</script>

<div class="about-container">
  <div class="about-section about-section--margin-top-{marginTopSize}">
    <div class="summary">
      <div class="summary__wrapper">
        <SectionTitle>{leftSectionTitle}</SectionTitle>
      </div>

      <div
        class="description description--{leftSectionFontSize} description--content-type-{contentUsedAsSummaryOrBody}"
      >
        <slot name="left" />
      </div>
    </div>
  </div>
</div>

<style lang="scss">
  @import "../style/global.scss";

  .about-container {
    margin: 0 auto;
    max-width: 72rem;
    position: relative;
    z-index: 1;
  }

  .about-section {
    display: grid;
    grid-template-columns: 1fr;
    padding: 96px;
    gap: 88px;
    font-family: $primary-font;
    z-index: 2;
    position: relative;

    &--margin-top-large {
      margin-top: 300px;
    }
    &--margin-top-medium {
      margin-top: 120px;
    }

    &--margin-top-small {
      margin-top: 0px;
      padding: 0px 96px 0px 96px;
    }

    @include mediumBreakpoint {
      grid-template-columns: 1fr;
      margin-top: 120px;

      &--margin-top-small {
        margin-top: 0px;
        padding: 0px 96px 0px 96px;
      }
    }
    @include smallBreakpoint {
      padding: 32px;
    }

    & .summary {
      &__wrapper {
        @include smallBreakpoint {
          display: flex;
          flex-direction: row;
          justify-content: center;
        }
      }

      & .description {
        font-weight: 200;
        margin-top: 40px;
        border-left: 3px solid $text-primary;
        padding-left: 40px;

        &--content-type-body {
          border-left: none;
          padding-left: 0px;
        }

        &--large {
          font-size: 48px;
          line-height: 62px;
        }
        &--small {
          font-size: 24px;
          line-height: 40px;
        }

        @include smallBreakpoint {
          font-size: 20px;
          line-height: 32px;
          padding-left: 16px;
        }

        ul,
        ul li {
          list-style: circle;
        }
      }
    }
  }
</style>
