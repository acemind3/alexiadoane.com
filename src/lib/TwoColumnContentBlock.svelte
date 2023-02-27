<script lang="ts">
  import SectionTitle from "./SectionTitle.svelte";

  export let leftSectionTitle: string;
  export let rightSectionTitle: string;
  export let rightSectionItems: string[];
  export let leftSectionFontSize: "large" | "small" = "large";
  export let marginTopSize: "medium" | "large" = "large";
</script>

<div class="about-container">
  <div class="about-section about-section--margin-top-{marginTopSize}">
    <div class="summary">
      <div class="summary__wrapper">
        <SectionTitle>{leftSectionTitle}</SectionTitle>
      </div>

      <div class="description description--{leftSectionFontSize}">
        <slot name="left" />
      </div>
    </div>

    <div class="hobby">
      <SectionTitle>{rightSectionTitle}</SectionTitle>
      <div class="hobby-list">
        <ul>
          {#each rightSectionItems as item}
            <li>{item}</li>
          {/each}
        </ul>
      </div>
    </div>
  </div>
</div>

<style lang="scss">
  @import "../style/global.scss";

  .about-container {
    margin: 0 auto;
    max-width: 115rem;
    position: relative;
    z-index: 1;
  }

  .about-section {
    display: grid;
    grid-template-columns: 3fr 1fr;
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

    @include mediumBreakpoint {
      grid-template-columns: 1fr;
      margin-top: 120px;
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
        border-left: 3px solid $charcoal;
        padding-left: 40px;

        &--large {
          font-size: 48px;
          line-height: 62px;
        }
        &--small {
          font-size: 24px;
          line-height: 40px;
        }

        @include smallBreakpoint {
          font-size: 24px;
          line-height: 40px;
        }

        ul,
        ul li {
          list-style: circle;
        }
      }
    }

    & .hobby {
      @include smallBreakpoint {
        display: flex;
        flex-direction: column;
        align-items: center;
      }

      & .hobby-list {
        & ul {
          padding-left: 0px;
          margin-top: 56px;
        }

        & li {
          list-style-type: none;
          margin-bottom: 24px;
          font-size: 24px;
          font-weight: 200;
          line-height: 34px;

          @include smallBreakpoint {
            text-align: center;
          }
        }
      }
    }
  }
</style>
