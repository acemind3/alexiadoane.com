<script lang="ts">
  export let href = "";
</script>

<a {href} target="blank" class="ace-link">
  <slot />
</a>

<style lang="scss">
  @import "../style/global.scss";

  .ace-link {
    color: $button-fill;
    text-decoration: underline;
    transition: color 0.25s linear;

    &:hover {
      color: $link-color;
    }
  }
</style>
