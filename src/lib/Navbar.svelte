<script lang="ts">
  import { onMount, onDestroy } from "svelte";
  const scrollNavBar = 800;
  let show = false;
  let runSlideOutAnimation = false;
  onMount(() => {
    const elem = document.getElementById("app");

    elem.onscroll = () => {
      if (elem.scrollTop > scrollNavBar) {
        show = true;
      } else if (elem.scrollTop == 0) {
        runSlideOutAnimation = false;
        show = false;
      } else {
        if (show === true) {
          runSlideOutAnimation = true;
          setTimeout(() => {
            show = false;
            runSlideOutAnimation = false;
          }, 500);
        } else show = false;
      }
    };
  });

  onDestroy(() => {
    const elem = document.getElementById("app");

    elem.onscroll = () => {};
  });

  let modifierClass = "--space-apart";
  const pathName = window.location.pathname;

  const getHref = (jump: string) => (pathName === "/" ? jump : `/${jump}`);
</script>

<nav
  class="nav nav{modifierClass}"
  class:sticky={show && !runSlideOutAnimation}
  class:slideOut={runSlideOutAnimation}
>
  <div class="nav-container nav-container{modifierClass}">
    <a class="nav__link" href="/"> Alex Doane </a>

    <div class="nav__additional-links topBottomBordersOut">
      <a class="nav-jump-link" href={getHref("#about")}>about</a>
      <a class="nav-jump-link" href={getHref("#portfolio")}>portfolio</a>
      <a class="nav-jump-link" href={getHref("#contact")}>contact</a>
    </div>
  </div>
</nav>

<style lang="scss">
  @import "../style/global.scss";

  @keyframes in {
    0% {
      position: sticky;
      top: -100%;
    }
    100% {
      position: sticky;
      top: 0;
    }
  }
  @keyframes out {
    0% {
      transform: translateY(0);
    }
    100% {
      transform: translateY(-100%);
    }
  }

  .nav {
    background-color: $almost-white;

    &.sticky,
    &.slideOut {
      position: sticky;
      z-index: 5000;
      box-shadow: 0px 4px 7px rgba(0, 0, 0, 0.1);
    }

    &.sticky {
      animation: in 0.5s cubic-bezier(0.075, 0.82, 0.165, 1) forwards;
    }
    &.slideOut {
      animation: out 0.5s cubic-bezier(0.075, 0.82, 0.165, 1) forwards;
      top: 0;
    }

    .nav-container {
      display: flex;
      flex-direction: row;
      justify-content: flex-start;
      align-items: center;
      padding: 32px 64px;
      margin: auto;
      max-width: 83rem;

      &--space-apart {
        justify-content: space-between;
      }

      @include smallBreakpoint {
        justify-content: center;
        flex-direction: column;
        gap: 24px;
      }
    }
    &--center {
      justify-content: flex-start;

      @include smallBreakpoint {
        justify-content: center;
      }
    }

    &__link {
      font-size: 48px;
      font-family: $secondary-font;
      text-decoration: none;
      color: $charcoal;

      @include smallBreakpoint {
        font-size: 32px;
      }
    }

    &__additional-links {
      display: flex;
      flex-direction: row;
      gap: 32px;
      transition: all 0.3s;

      > .nav-jump-link {
        padding: 20px 10px;
        font-size: 16px;
        color: $charcoal;
        text-decoration: none;
        font-family: $primary-font;
        position: relative;

        &:before,
        &:after {
          position: absolute;
          left: 0px;
          height: 2px;
          background: $charcoal;
          content: "";
          opacity: 0;
          transition: all 0.3s;
          width: 100%;
        }
        &:before {
          transform: translateY(0px);
        }
        &:after {
          transform: translateY(0px);
        }

        &:hover {
          &:before,
          &:after {
            opacity: 1;
          }
          &:before {
            transform: translateY(23px);
          }
          &:after {
            transform: translateY(-11px);
          }
        }
      }
    }
  }
</style>
