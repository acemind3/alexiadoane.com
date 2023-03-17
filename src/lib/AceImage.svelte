<script lang="ts">
  let previewOpen = false;

  function togglePreview() {
    previewOpen = !previewOpen;
  }
</script>

<div
  class="ace-image"
  role="button"
  on:click={togglePreview}
  on:keyup={togglePreview}
>
  <slot />
</div>
<div class="ace-image__preview" class:ace-image__preview--open={previewOpen}>
  <div
    class="ace-image__preview-backdrop"
    on:click={togglePreview}
    on:keyup={togglePreview}
  >
    <button
      class="ace-image__preview-close"
      on:click={togglePreview}
      on:keyup={togglePreview}>X</button
    >
    <div class="ace-image__preview-content">
      <slot />
    </div>
  </div>
</div>

<style lang="scss">
  .ace-image__preview {
    display: none;
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vw;
    z-index: 100;

    &--open {
      display: flex;
      flex-direction: row;
      justify-content: center;
      align-items: center;
    }

    &-backdrop {
      width: 100%;
      height: 100%;
      margin: 0;
      padding: 0;
      position: relative;
      background-color: rgba(#1c1c1c, 0.8);
      backdrop-filter: blur(15px);
    }

    &-close {
      position: absolute;
      top: 5%;
      right: 5%;
      font-size: 16px;
    }

    &-content {
      width: auto;
      max-width: 80vw;
      height: calc(100vh - 260px);
      margin: 130px auto;

      img {
        width: 100%;
        height: auto;
      }
    }
  }
</style>
