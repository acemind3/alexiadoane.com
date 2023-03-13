<script lang="ts">
  import { onMount } from "svelte";

  const top = 0;
  const left = 0;
  const bottom = 0;
  const right = 0;
  let playWaveAnimation = false;
  let container;
  let video: HTMLVideoElement;
  let waveInterval: NodeJS.Timer;

  onMount(() => {
    if (typeof IntersectionObserver !== "undefined") {
      const rootMargin = `${bottom}px ${left}px ${top}px ${right}px`;

      const observer = new IntersectionObserver(
        (entries) => {
          const isIntersecting = entries[0].isIntersecting;

          if (isIntersecting) {
            playWaveAnimation = true;

            onBirbAnimate();

            waveInterval = setInterval(() => {
              onWaveAnimate();
            }, 6000);
          } else {
            playWaveAnimation = false;
            if (waveInterval) clearInterval(waveInterval);
            onBirbStopAnimating();
          }
        },
        {
          rootMargin,
        }
      );

      observer.observe(container);
      return () => observer.unobserve(container);
    }
  });
  function onWaveAnimate() {
    playWaveAnimation = true;

    setTimeout(() => {
      playWaveAnimation = false;
    }, 5000);
  }
  function onBirbAnimate() {
    if (video) {
      video.currentTime = 0;
      video.play();
    }
  }

  function onBirbStopAnimating() {
    if (video) {
      video.pause();
      video.currentTime = 0;
    }
  }

  const blocks: number[] = new Array(45).fill(1);
</script>

<div bind:this={container} class="ace-divider">
  <div class="ace-divider__sound-wave">
    {#each blocks as block, index}
      <div
        class="ace-divider__sound-wave-block ace-divider__sound-wave-block-{index +
          1}"
        class:ace-divider__sound-wave-block-intersecting={playWaveAnimation}
      />
    {/each}
  </div>
  <div class="ace-divider__line">
    <div class="ace-divider__line-bird-wrapper">
      <video
        preload="none"
        bind:this={video}
        playsinline
        muted
        class="skatebird-vid"
        loop
      >
        <source src="/skatebirb-vp9-chrome.webm" type="video/webm" />
        <source src="/skatebirb-hevc-safari.mp4" type="video/mp4" />
      </video>
      <!-- <div class="ace-divider__line-bird ace-divider__line-bird-1">
        <svg
          width="40"
          height="86"
          viewBox="0 0 40 86"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <g clip-path="url(#clip0_103_2685)">
            <path
              d="M26.0363 46.731C28.9168 40.9747 34.4167 28.2781 34.4167 23.1976C34.4167 18.1172 34.0765 15.9172 31.9604 14.0528C31.3684 10.3286 30.096 7.19645 34.4167 4.65621C38.7375 2.11596 39.7489 1.61258 39.7489 1.61258C39.7489 1.61258 31.3684 1.36088 31.2006 1.10453C31.0328 0.848174 29.1684 0.0884322 26.9638 -0.000126713C24.7591 -0.0886856 17.9914 1.60792 15.7028 5.33205C13.4143 9.05618 12.5706 12.1045 11.0465 12.8642C9.52235 13.624 2.49824 18.4527 1.64993 29.4574C0.801633 40.462 0.125787 44.27 1.14188 52.4827C2.15798 60.6953 2.24188 64.3356 2.24188 65.9436C2.24188 67.5517 -0.638616 78.9804 0.125787 83.3804C0.89019 87.7804 2.58213 85.5804 3.00628 84.2287C5.20627 85.9906 9.69481 84.3965 9.9465 78.8965C10.1982 73.3966 11.3029 65.7758 11.3029 65.7758C11.3029 65.7758 17.777 58.7517 19.8744 55.8712C21.9719 52.9907 26.0316 46.7263 26.0316 46.7263L26.0363 46.731Z"
              fill="#3C3C3C"
            />
          </g>
          <defs>
            <clipPath id="clip0_103_2685">
              <rect
                width="39.749"
                height="86"
                fill="white"
                transform="matrix(-1 0 0 1 39.7489 0)"
              />
            </clipPath>
          </defs>
        </svg>
      </div>
      <div class="ace-divider__line-bird ace-divider__line-bird-2">
        <svg
          width="105"
          height="90"
          viewBox="0 0 105 90"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M69 88.7556L62.7735 83.354V82.3566L61.1125 80.7767V79.8617L58.9548 78.117C58.9548 78.117 58.7049 76.2047 58.458 75.5398C58.2111 74.8748 58.458 74.46 58.458 74.46L56.6324 71.3032L58.2111 72.3006C58.2111 72.3006 57.7144 70.3882 56.6324 69.5586C55.5505 68.729 54.307 67.8963 54.307 67.8963L56.2179 68.3935L54.8068 67.2314H57.1322C57.1322 67.2314 55.139 65.5692 54.7246 65.2367C54.3101 64.9043 53.8102 62.6594 53.0636 61.8298C52.3169 61.0002 52.899 59.5026 51.1526 57.6757C49.4063 55.8487 47.2516 52.9389 43.762 52.0239C40.2724 51.1089 40.9398 50.7765 40.9398 50.7765L41.3543 49.8615L40.2754 48.614V48.1168L39.3611 47.5343L40.0255 46.7047L39.3611 46.1221L40.1901 45.4572L37.118 44.7923H40.2723L38.6114 44.3775L40.6045 43.8803L38.4468 43.4655L40.7722 42.6359C40.7722 42.6359 38.8613 42.6359 37.118 42.9684C38.5291 41.971 39.2758 41.5562 39.2758 41.5562C39.2758 41.5562 36.286 41.3915 34.8749 42.3035C36.8681 40.3911 37.947 39.229 37.947 39.229L34.2928 41.2237L36.7827 37.5667L35.204 39.0613L36.033 37.5667L32.711 39.8939L35.6185 35.9045L33.8752 36.9842L35.1217 35.1572L34.7072 34.66L33.6284 35.4897L33.7929 33.2448L30.3886 36.9842H28.8953L31.303 34.5746L31.5529 33.2448L30.1418 33.9921C30.1418 33.9921 32.4672 31 32.135 31C31.8028 31 29.4774 32.5799 28.8953 32.7446C28.3132 32.9093 26.9021 34.0744 26.9021 34.0744H25.5733L23.4155 36.6517L27.4019 31.6649L22.3366 36.6517L21.0078 37.5667L23.3332 33.4126L20.0112 37.9815V36.8195C20.0112 36.8195 18.7647 38.8142 18.018 40.7235C17.2713 42.6329 15.8602 43.6333 14.8636 46.7077C10.7127 48.0375 1.26412e-06 51.112 1.26412e-06 51.112C1.26412e-06 51.112 13.1204 52.5241 13.4495 52.5241C13.7787 52.5241 16.0248 54.2688 17.186 55.5162C17.186 55.5162 15.6926 57.3432 15.6073 59.8778C15.522 62.4124 14.3608 67.4815 21.5015 75.5398C28.6423 83.598 31.9643 84.9308 31.9643 84.9308C31.9643 84.9308 39.5196 85.0955 43.4237 84.6807C47.3278 84.2659 52.9721 86.343 52.9721 86.343L57.2907 86.9256L56.9585 84.5984L63.6025 90H66.0925L65.9279 89.2527L67.339 90L69 89.6675V88.7525L69 88.7556Z"
            fill="#3C3C3C"
          />
        </svg>
      </div> -->
    </div>
  </div>
</div>

<style lang="scss">
  @import "../style/global.scss";
  $numberOfBlocks: 45;
  $gutterWidth: 4px;
  $blockWidth: 3px;
  $blockHeight: 50px;
  $soundWaveWidth: calc(($gutterWidth + $blockWidth) * $numberOfBlocks);

  @keyframes scaleSoundWaves {
    0% {
      transform: scaleY(var(--start-height, 1));
    }

    50% {
      transform: scaleY(var(--end-height, 2));
    }
    100% {
      transform: scaleY(var(--start-height, 1));
    }
  }

  .ace-divider {
    display: flex;
    align-items: center;
    flex-direction: row;
    justify-content: flex-start;
    gap: 0;
    margin-top: 120px;
    &__sound-wave {
      display: flex;
      flex-direction: row;
      gap: $gutterWidth;
      width: $soundWaveWidth;

      &-block {
        width: $blockWidth;
        height: $blockHeight;
        background-color: $background-accent;

        &-intersecting {
          animation: 2s scaleSoundWaves ease-in-out forwards;
        }

        @for $i from 1 through $numberOfBlocks {
          &-#{$i} {
            animation-delay: calc(50ms * $i);
            transform: scaleY(var(--start-height, 1));
          }
        }
        //FIRST SECTION START
        &-1 {
          --start-height: 1.5;
          --end-height: 1.4;
        }
        &-2 {
          --start-height: 0.6;
          --end-height: 1;
        }
        &-3 {
          --start-height: 0.2;
          --end-height: 0.8;
        }
        &-4 {
          --start-height: 1.2;
          --end-height: 1.25;
        }
        &-5 {
          --start-height: 0.85;
          --end-height: 1.25;
        }
        &-6 {
          --start-height: 0.75;
          --end-height: 0.6;
        }
        //FIRST SECTION END
        &-7 {
          --start-height: 0.2;
          --end-height: 0.6;
        }
        //SECOND SECTION START
        &-8 {
          --start-height: 1;
          --end-height: 2.2;
        }
        &-9 {
          --start-height: 1.2;
          --end-height: 2.4;
        }
        &-10 {
          --start-height: 1.4;
          --end-height: 2.6;
        }
        &-11 {
          --start-height: 1.6;
          --end-height: 2.4;
        }
        &-12 {
          --start-height: 1.8;
          --end-height: 2.2;
        }
        &-13 {
          --start-height: 1.9;
          --end-height: 0.6;
        }
        &-14 {
          --start-height: 2;
          --end-height: 0.6;
        }
        &-15 {
          --start-height: 1.6;
          --end-height: 1.6;
        }
        &-16 {
          --start-height: 2.3;
          --end-height: 1.65;
        }
        &-17 {
          --start-height: 2;
          --end-height: 1.7;
        }
        &-18 {
          --start-height: 1.8;
          --end-height: 1.7;
        }
        &-19 {
          --start-height: 1.5;
          --end-height: 1.6;
        }
        &-20 {
          --start-height: 0.75;
          --end-height: 1.5;
        }
        //SECOND SECTION END
        &-21 {
          --start-height: 0.3;
          --end-height: 1.5;
        }
        &-22 {
          --start-height: 0.5;
          --end-height: 1.5;
        }
        &-23 {
          --start-height: 0.75;
          --end-height: 1.5;
        }
        &-24 {
          --start-height: 1;
          --end-height: 1.5;
        }
        &-25 {
          --start-height: 0.75;
          --end-height: 1.5;
        }
        &-26 {
          --start-height: 0.5;
          --end-height: 1.65;
        }
        &-27 {
          --start-height: 0.3;
          --end-height: 1.7;
        }
        //THIRD SECTION END
        &-28 {
          --start-height: 1;
          --end-height: 1.7;
        }
        &-29 {
          --start-height: 0.8;
          --end-height: 1.7;
        }
        &-30 {
          --start-height: 0.6;
          --end-height: 1.7;
        }
        &-31 {
          --start-height: 0.4;
          --end-height: 1.2;
        }
        //FOURTH SECITON END
        &-32 {
          --start-height: 1.3;
          --end-height: 1.25;
        }
        &-33 {
          --start-height: 1.6;
          --end-height: 1.8;
        }
        &-34 {
          --start-height: 1.8;
          --end-height: 1.25;
        }
        &-35 {
          --start-height: 2;
          --end-height: 1.25;
        }
        &-36 {
          --start-height: 1.8;
          --end-height: 0.6;
        }
        &-37 {
          --start-height: 1.6;
          --end-height: 0.6;
        }
        &-38 {
          --start-height: 2.5;
          --end-height: 2.2;
        }
        &-39 {
          --start-height: 1.8;
          --end-height: 2.4;
        }
        &-40 {
          --start-height: 1.4;
          --end-height: 2.6;
        }
        &-41 {
          --start-height: 2.1;
          --end-height: 0.6;
        }
        &-42 {
          --start-height: 0.9;
          --end-height: 2.2;
        }
        &-43 {
          --start-height: 0.7;
          --end-height: 2.4;
        }
        &-44 {
          --start-height: 0.4;
          --end-height: 2.6;
        }
        &-45 {
          --start-height: 0.2;
          --end-height: 2.6;
        }
      }
    }

    &__line {
      width: calc(100vw - $soundWaveWidth);
      height: 4px;
      background-color: $background-accent;
      position: relative;
      &-bird {
        width: 120px;
        height: auto;
        position: absolute;

        svg path {
          fill: $background-accent;
        }

        &-wrapper {
          position: relative;
          right: -3vw;

          .skatebird-vid {
            position: absolute;
            top: -170px;
            right: 65px;
            max-width: 240px;
            height: auto;
            transform: scaleX(-1);
            opacity: $theme-divider-opacity;

            @include smallBreakpoint {
              right: -30px;
            }

            @media screen and (max-width: 478px) {
              display: none;
            }
          }
        }

        // &-1 {
        //   right: 122px;
        //   top: -52px;
        //   @include smallBreakpoint {
        //     right: 52px;
        //   }

        //   @media screen and (max-width: 478px) {
        //     display: none;
        //   }
        // }

        // &-2 {
        //   right: 80px;
        //   top: -84px;
        //   @include smallBreakpoint {
        //     right: 4px;
        //   }

        //   @media screen and (max-width: 445px) {
        //     display: none;
        //   }
        // }
      }
    }
  }
</style>
