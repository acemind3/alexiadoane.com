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
            width="80"
            height="80"
            viewBox="0 0 80 80"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              fill-rule="evenodd"
              clip-rule="evenodd"
              d="M40 0C17.9086 0 0 17.9086 0 40C0 62.0914 17.9086 80 40 80C62.0914 80 80 62.0914 80 40C80 17.9086 62.0914 0 40 0ZM19.2027 33.1297H28.2676V60.3659H19.2027V33.1297ZM28.8646 24.7045C28.8058 22.034 26.8961 20 23.7951 20C20.694 20 18.6667 22.034 18.6667 24.7045C18.6667 27.3197 20.6341 29.4122 23.6774 29.4122H23.7353C26.8961 29.4122 28.8646 27.3197 28.8646 24.7045ZM50.5219 32.4902C56.487 32.4902 60.959 36.3838 60.959 44.7495L60.9586 60.3659H51.8941V45.7946C51.8941 42.1345 50.5824 39.637 47.3008 39.637C44.7965 39.637 43.3048 41.3207 42.6496 42.9469C42.41 43.5297 42.3511 44.3417 42.3511 45.1557V60.3667H33.2852C33.2852 60.3667 33.4046 35.6862 33.2852 33.1305H42.3511V36.9882C43.5543 35.1337 45.709 32.4902 50.5219 32.4902Z"
              fill="url(#paint0_linear_4_65)"
            />
            <defs>
              <linearGradient
                id="paint0_linear_4_65"
                x1="40"
                y1="0"
                x2="40"
                y2="80"
                gradientUnits="userSpaceOnUse"
              >
                <stop stop-color="#3A5DDC" />
                <stop offset="1" stop-color="#997ADD" />
              </linearGradient>
            </defs>
          </svg>
        </a>
        <a
          class="social-media-links"
          href="/alex-web-resume.pdf"
          target="blank"
        >
          <svg
            class="social-media-links__icons"
            width="80"
            height="80"
            viewBox="0 0 80 80"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              fill-rule="evenodd"
              clip-rule="evenodd"
              d="M40 80C62.0914 80 80 62.0914 80 40C80 17.9086 62.0914 0 40 0C17.9086 0 0 17.9086 0 40C0 62.0914 17.9086 80 40 80ZM57.9089 28.3826L49.0266 19.2932C48.2033 18.4592 47.0727 17.9926 45.8946 18.0008H25.3482C25.008 17.9891 24.6765 18.1096 24.4245 18.3366C24.1726 18.5636 24.0201 18.8789 24 19.2156V60.334C24.0111 60.6771 24.1596 61.0015 24.4124 61.2358C24.6653 61.4704 25.002 61.5956 25.3482 61.5842H57.6518C57.998 61.5956 58.3346 61.4704 58.5876 61.2358C58.8405 61.0015 58.9889 60.6771 59 60.334V31.0244C58.9946 30.0375 58.6039 29.0905 57.9089 28.3826ZM54.2918 29.5057L54.2654 29.5057L54.2635 29.5055L54.2918 29.5057ZM54.2654 29.5057L48.2634 29.5054C48.1462 29.5092 48.0322 29.4669 47.9465 29.3875C47.8608 29.3077 47.8105 29.198 47.807 29.0817V22.8243C47.8137 22.6317 47.9411 22.4639 48.1258 22.404C48.3109 22.3441 48.5141 22.4046 48.6345 22.556L54.6342 28.7995C54.7555 28.931 54.7813 29.123 54.6982 29.281C54.6157 29.4381 54.4428 29.5279 54.2654 29.5057ZM55.5403 59.0276H55.5275L55.512 59.027L55.5403 59.0276ZM55.5275 59.0276L27.4887 59.0273C27.0947 59.0273 26.7752 58.7114 26.7752 58.3211V21.2207C26.7752 20.8307 27.0947 20.5144 27.4887 20.5144H44.3115C44.508 20.5028 44.7007 20.5721 44.8437 20.7058C44.987 20.8395 45.0679 21.0259 45.0676 21.2207V31.1084C45.087 31.6558 45.5491 32.0849 46.1021 32.0691H54.9126C55.2594 32.0593 55.5964 32.1864 55.8489 32.4219C56.1015 32.6575 56.2496 32.9825 56.261 33.3262V58.328C56.2591 58.5203 56.1782 58.7035 56.0368 58.8356C55.8992 58.9642 55.716 59.0331 55.5275 59.0276ZM36.7162 32.5284C38.6279 32.5284 40.1792 30.1065 40.1792 28.2086C40.1237 27.0211 39.4511 25.9465 38.401 25.368C37.3513 24.7895 36.0731 24.7895 35.0234 25.368C33.9733 25.9465 33.301 27.0211 33.2456 28.2086C33.2456 30.1069 34.8044 32.5284 36.7162 32.5284ZM42.8209 37.1409V41.4433H30.6039V37.1409C30.6008 36.3644 30.8353 35.606 31.2755 34.9709C31.7156 34.3358 32.3392 33.8558 33.06 33.597L36.5486 39.3382L40.0789 33.5188C40.8651 33.7314 41.56 34.2016 42.0559 34.8567C42.5518 35.5117 42.8205 36.3148 42.8209 37.1409ZM39.5188 33.5188L36.5471 38.1414L33.5979 33.5543L33.5754 33.5188L39.5188 33.5188ZM31.2081 47.3867H45.8484C46.3646 47.3867 46.783 46.943 46.783 46.3959C46.783 45.8488 46.3645 45.4055 45.8484 45.4055H31.2081C30.692 45.4055 30.2736 45.8488 30.2736 46.3959C30.2736 46.9431 30.692 47.3867 31.2081 47.3867ZM45.8484 51.3492H31.2081C30.692 51.3492 30.2736 50.9798 30.2736 50.5239C30.2736 50.0679 30.692 49.6982 31.2081 49.6982H45.8484C46.3645 49.6982 46.783 50.0679 46.783 50.5239C46.783 50.9798 46.3646 51.3492 45.8484 51.3492ZM31.2081 55.6415H45.8484C46.3646 55.6415 46.783 55.198 46.783 54.651C46.783 54.1039 46.3645 53.6604 45.8484 53.6604H31.2081C30.692 53.6604 30.2736 54.1039 30.2736 54.651C30.2736 55.198 30.692 55.6415 31.2081 55.6415Z"
              fill="url(#paint0_linear_102_2573)"
            />
            <defs>
              <linearGradient
                id="paint0_linear_102_2573"
                x1="40"
                y1="0"
                x2="40"
                y2="80"
                gradientUnits="userSpaceOnUse"
              >
                <stop stop-color="#3A5DDC" />
                <stop offset="1" stop-color="#997ADD" />
              </linearGradient>
            </defs>
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

        &:hover {
          opacity: 0.5;
        }
      }
    }
  }
</style>
