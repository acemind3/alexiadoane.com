<script lang="ts">
  export let href: string = "";

  export let hasIcon: boolean = true;
</script>

<div class="button__wrapper">
  <a class="button" {href} target="_blank" rel="noreferrer">
    <slot />

    {#if hasIcon}
      <svg
        class="button__icon"
        width="16"
        height="16"
        viewBox="0 0 16 16"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          fill-rule="evenodd"
          clip-rule="evenodd"
          d="M12 8.80001C12 8.35822 12.3582 8.00001 12.8 8.00001C13.2418 8.00001 13.6 8.35822 13.6 8.80001V13.6C13.6 14.9255 12.5255 16 11.2 16H2.4C1.07447 16 0 14.9255 0 13.6V4.8C0 3.47447 1.07447 2.4 2.4 2.4H7.20001C7.64179 2.4 8.00001 2.75821 8.00001 3.2C8.00001 3.64179 7.64179 4 7.20001 4H2.4C1.95821 4 1.6 4.35822 1.6 4.8V13.6C1.6 14.0418 1.95821 14.4 2.4 14.4H11.2C11.6418 14.4 12 14.0418 12 13.6V8.80001Z"
          fill="#3A5DDC"
        />
        <path
          fill-rule="evenodd"
          clip-rule="evenodd"
          d="M14.3996 1.6H10.3996C9.95782 1.6 9.59961 1.24179 9.59961 0.800001C9.59961 0.358213 9.95782 0 10.3996 0H15.1996C15.6414 0 15.9996 0.358213 15.9996 0.800001V5.6C15.9996 6.04179 15.6414 6.4 15.1996 6.4C14.7578 6.4 14.3996 6.04179 14.3996 5.6V1.6Z"
          fill="#3A5DDC"
        />
        <path
          fill-rule="evenodd"
          clip-rule="evenodd"
          d="M6.96601 10.1659C6.65351 10.4783 6.14709 10.4783 5.83458 10.1659C5.52226 9.85345 5.52226 9.34702 5.83458 9.03451L14.6346 0.234507C14.9471 -0.077813 15.4535 -0.077813 15.766 0.234507C16.0783 0.547006 16.0783 1.05343 15.766 1.36594L6.96601 10.1659Z"
          fill="#3A5DDC"
        />
      </svg>
    {/if}
  </a>
</div>

<style lang="scss">
  @import "../style/global.scss";
  .button {
    clip-path: polygon(100% 0, 100% 77%, 93% 100%, 0 100%, 0 0);
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25),
      inset 2px 3px 2px rgba(255, 255, 255, 0.25);
    font-size: 16px;
    text-transform: uppercase;
    font-weight: 500;
    font-family: $primary-font;
    padding: 16px;
    width: fit-content;
    height: fit-content;
    letter-spacing: 2px;
    text-decoration: none;
    background-color: $background-secondary;
    color: $text-primary;
    display: block;
    transition: all 0.5s linear;

    @include mediumBreakpoint {
      &:hover {
        &:before {
          top: 50%;
        }
      }
    }

    &:before {
      content: "";
      position: absolute;
      background: $cool-gradient;
      bottom: 0;
      left: 0;
      right: 0;
      top: 100%;
      z-index: -1;
      -webkit-transition: top 0.5s linear;
    }

    &:hover {
      color: $background-secondary;

      svg path {
        fill: $background-secondary;
      }

      &:before {
        top: 0%;
      }
    }

    &__wrapper {
      clip-path: polygon(100% 0, 100% 77%, 93% 100%, 0 100%, 0 0);
      background: $cool-gradient;
      padding: 2px;
      width: fit-content;
      height: fit-content;
    }

    &__icon {
      margin-left: 6px;
      width: 16px;
      height: 16px;
      path {
        fill: $button-fill;
        transition: fill 0.5s linear;
      }
    }
    &:focus {
      border-left: 4px solid yellow;
    }
  }
</style>
