<script lang="ts">
  export let href = "";
</script>

<a {href} target="_blank" class="ace-link">
  <slot />
</a>

<style lang="scss">
  @import "../style/global.scss";

  .ace-link {
    color: $thick-blue;
    text-decoration: underline;
    transition: color 0.25s linear;

    &:hover {
      color: $royal-lavender;
    }
  }
</style>
