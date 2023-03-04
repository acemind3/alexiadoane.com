<script lang="ts">
  let theme: "light" | "dark" =
    (localStorage.getItem("theme") as "light" | "dark") ?? "light";

  const toggleDarkMode = () => {
    const hasLightMode = document.body.classList.contains("color__light");
    localStorage.setItem("theme", hasLightMode ? "dark" : "light");

    document.body.classList.toggle("color__light");
    document.body.classList.toggle("color__dark");
    theme = theme === "light" ? "dark" : "light";
  };
</script>

<button class="ace-theme-toggle" on:click={toggleDarkMode}>
  make it {theme == "light" ? "dark" : "light"}

  {#if theme === "light"}
    <svg
      width="18"
      height="18"
      viewBox="0 0 18 18"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
      class="ace-theme-toggle__icon"
    >
      <path
        d="M7.76973 10.2301C4.82442 7.28487 4.22065 3.07482 6.94888 0C5.38271 0.384045 3.89842 1.18746 2.67465 2.411C-0.891549 5.97712 -0.891549 11.7588 2.67465 15.3254C6.24085 18.8915 12.0227 18.8915 15.5889 15.3254C16.8125 14.1019 17.6159 12.6176 18 11.0513C14.9249 13.7793 10.7148 13.1755 7.76965 10.2303L7.76973 10.2301Z"
        fill="black"
      />
    </svg>
  {/if}
  {#if theme === "dark"}
    <svg
      width="25"
      height="25"
      viewBox="0 0 25 25"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
      class="ace-theme-toggle__icon"
    >
      <path
        d="M18.8488 12.4999C18.8488 16.0062 16.0063 18.8487 12.5 18.8487C8.99378 18.8487 6.15125 16.0062 6.15125 12.4999C6.15125 8.99369 8.99378 6.15115 12.5 6.15115C16.0063 6.15115 18.8488 8.99369 18.8488 12.4999Z"
        fill="black"
      />
      <path d="M11.2303 0H13.7697V4.289H11.2303V0Z" fill="black" />
      <path d="M11.2303 20.711H13.7697V25H11.2303V20.711Z" fill="black" />
      <path
        d="M20.7111 11.2302H25.0001V13.7696H20.7111V11.2302Z"
        fill="black"
      />
      <path d="M0 11.2302H4.289V13.7696H0V11.2302Z" fill="black" />
      <path
        d="M2.78235 4.56194L4.57799 2.7663L7.61069 5.79899L5.81505 7.59464L2.78235 4.56194Z"
        fill="black"
      />
      <path
        d="M17.3891 19.2004L19.1847 17.4048L22.2174 20.4375L20.4218 22.2331L17.3891 19.2004Z"
        fill="black"
      />
      <path
        d="M17.4047 5.81508L20.4374 2.78238L22.2331 4.57802L19.2004 7.61072L17.4047 5.81508Z"
        fill="black"
      />
      <path
        d="M2.76624 20.4218L5.79893 17.3891L7.59458 19.1847L4.56188 22.2174L2.76624 20.4218Z"
        fill="black"
      />
    </svg>
  {/if}
</button>

<style lang="scss">
  @import "../style/global.scss";

  .ace-theme-toggle {
    padding: 6px 16px;
    font-size: 14px;
    display: flex;
    flex-direction: row;
    align-items: center;
    max-width: 140px;
    cursor: pointer;
    color: $text-primary;
    line-height: 16px;
    height: 40px;
    // border: none;
    // background-color: $background-light;
    // box-shadow: $theme-toggle-box-shadow;
    border: 1px solid $text-secondary;
    background-color: $background-secondary;

    &__icon {
      margin-left: 12px;
      width: 14px;
      height: 14px;
      path {
        fill: $text-primary;
      }
    }
  }
</style>
