<script lang="ts">
  type BackgroundType = "background" | "no-background";

  export let backgroundType: BackgroundType = "no-background";
</script>

<footer id="contact" class="footer footer__{backgroundType}">
  <div class="footer__container">
    <div class="footer__content">
      <div class="call-to-action">
        <h3>Let’s get in touch</h3>
      </div>
      <div class="social-media-wrapper">
        <a
          class="social-media-links"
          href="https://www.linkedin.com/in/alex-doane-67a63171/"
          target="blank"
        >
          <svg
            class="social-media-links__icons"
            width="40"
            height="37"
            viewBox="0 0 40 37"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M8.43956 11.2529H0V36.5716H8.43956V11.2529Z"
              fill="white"
            />
            <path
              d="M4.92308 8.43956C7.64202 8.43956 9.84615 6.5503 9.84615 4.21978C9.84615 1.88926 7.64202 0 4.92308 0C2.20414 0 0 1.88926 0 4.21978C0 6.5503 2.20414 8.43956 4.92308 8.43956Z"
              fill="white"
            />
            <path
              d="M29.5384 11.2529H28.7944C25.7181 11.2529 23.1666 13.4641 22.6222 16.3828H22.5055V11.2529H14.0659V36.5716H22.5055V24.4918V22.3411C22.5153 21.808 22.5575 21.3157 22.6236 20.8501C23.0569 18.9794 24.7237 17.5826 26.7253 17.5826C29.056 17.5826 30.945 19.4717 30.945 21.8024V22.5887V24.2428V36.5716H39.3846V23.7463V22.5887V21.0991C39.3846 15.6612 34.9763 11.2529 29.5384 11.2529Z"
              fill="white"
            />
          </svg>
        </a>
        <a
          class="social-media-links"
          href="/alex-web-resume.pdf"
          target="blank"
        >
          <svg
            class="social-media-links__icons"
            width="33"
            height="41"
            viewBox="0 0 33 41"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M24.75 0H2.0625C0.824926 0 0 0.819927 0 2.05V38.95C0 40.1801 0.824926 41 2.0625 41H30.9375C32.1751 41 33 40.1801 33 38.95V8.2L24.75 0ZM16.5 6.15C18.7688 6.15 20.625 7.99493 20.625 10.25C20.625 12.5051 18.7688 14.35 16.5 14.35C14.2312 14.35 12.375 12.5051 12.375 10.25C12.375 7.99493 14.2312 6.15 16.5 6.15ZM16.5 16.4C21.0376 16.4 24.75 20.0899 24.75 24.6H8.25C8.25 20.0899 11.9624 16.4 16.5 16.4ZM26.8125 34.85H6.1875C4.94993 34.85 4.125 34.0301 4.125 32.8C4.125 31.5699 4.94993 30.75 6.1875 30.75H26.8125C28.0501 30.75 28.875 31.5699 28.875 32.8C28.875 33.825 28.0501 34.85 26.8125 34.85Z"
              fill="#FBFBFB"
            />
          </svg>
        </a>
      </div>
    </div>
  </div>
</footer>

<style lang="scss">
  @import "../style/global.scss";

  .footer {
    position: relative;
    z-index: 1;

    &__background {
      background-color: $background-secondary;
    }
    &__container {
      margin: 0 auto;
      max-width: 125rem;
    }

    &__content {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      align-items: center;
      padding: 96px;
      padding-top: 192px;

      @include mediumBreakpoint {
        flex-direction: column;
        gap: 32px;
        padding-bottom: 64px;
      }

      @include smallBreakpoint {
        padding: 32px;
        padding-top: 64px;
        padding-bottom: 120px;
      }
    }

    .call-to-action {
      font-family: $secondary-font;
      color: $text-primary;
      border-left: 3px solid $text-primary;
      font-size: 64px;
      padding-left: 40px;

      @include smallBreakpoint {
        font-size: 32px;
        padding-left: 32px;
      }
    }
    .social-media-wrapper {
      display: flex;
      flex-direction: row;
      justify-content: flex-end;
      gap: 16px;

      .social-media-links {
        transition: all 0.5s;
        opacity: 1;
        border: 2px solid $text-primary;
        padding: 16px;
        border-radius: 50%;
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;

        &__icons {
          width: 32px;
          height: 32px;

          path {
            fill: $text-primary;
            transition: all 0.5s;
          }
        }

        &:hover {
          border-color: $button-fill;
          .social-media-links__icons path {
            fill: $button-fill;
          }
        }
      }
    }
  }
</style>
