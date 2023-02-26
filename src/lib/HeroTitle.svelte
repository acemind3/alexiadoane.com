<script lang="ts">
  import Button from "./Button.svelte";
  import SectionTitle from "./SectionTitle.svelte";

  export let websiteUrl: string = null;
  export let tags: string[] = [];
  export let titleText: string = "";
</script>

<div class="hero-title">
  <h1 class="hero-title__heading">{titleText}</h1>
  <div class="hero-title__tags">
    {#each tags as tag}
      <SectionTitle>{tag}</SectionTitle>
    {/each}
  </div>
  {#if websiteUrl != null}
    <Button href={websiteUrl}>Visit Website</Button>
  {/if}
</div>

<style lang="scss">
  @import "../style/global.scss";

  .hero-title {
    display: flex;
    flex-direction: column;
    gap: 24px;
    background-color: $almost-white;
    margin-left: -100vw;
    padding-left: 100vw;
    margin-right: -100vw;
    padding-right: 100vw;
    padding-top: 141px;
    padding-bottom: 63px;

    @include mediumBreakpoint {
      margin-left: 0;
      padding-left: 96px;
      width: 100%;
      padding-top: 64px;
      padding-bottom: 64px;
    }

    @include smallBreakpoint {
      align-items: center;
      padding-left: 0;
    }

    &__heading {
      font-size: 80px;
      line-height: 82px;
      font-family: $secondary-font;
      max-width: 80vw;

      @include smallBreakpoint {
        text-align: center;
        font-size: 48px;
        line-height: 50px;
      }
    }
    &__tags {
      display: flex;
      flex-direction: row;
      gap: 12px;
      flex-wrap: wrap;
      margin-bottom: 32px;

      @include smallBreakpoint {
        flex-direction: column;
        align-items: center;
        gap: 24px;
      }

      & > * {
        width: 50%;

        @include smallBreakpoint {
          width: 100%;
        }
      }
    }
  }
</style>
