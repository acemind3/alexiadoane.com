<script lang="ts">
  import { Router, Route } from "svelte-routing";

  import HomePage from "./pages/home/HomePage.svelte";
  import BeerNuts from "./pages/portfolio/BeerNuts.svelte";
  import Tag from "./pages/portfolio/Tag.svelte";
  import Pixo from "./pages/portfolio/Pixo.svelte";
  import SaferIllinois from "./pages/portfolio/SaferIllinois.svelte";
  import Aptech from "./pages/portfolio/Aptech.svelte";
  import InteractiveComponent from "./pages/portfolio/InteractiveComponent.svelte";

  export let url = window.location.pathname;

  let colorScheme: "dark" | "light" = "light";
  let storedTheme: "dark" | "light" | undefined = localStorage.getItem(
    "theme"
  ) as "dark" | "light" | undefined;

  window
    .matchMedia("(prefers-color-scheme: dark)")
    .addEventListener("change", (event) => {
      colorScheme = event.matches ? "dark" : "light";
    });

  const shouldBeLightMode =
    storedTheme == undefined ? colorScheme == "light" : storedTheme == "light";

  if (storedTheme == undefined) {
    localStorage.setItem("theme", colorScheme);
  }

  const hasLightMode = document.body.classList.contains("color__light");
  const hasDarkMode = document.body.classList.contains("color__dark");

  if (shouldBeLightMode && !hasLightMode)
    document.body.classList.toggle("color__light");
  if (!shouldBeLightMode && !hasDarkMode) {
    document.body.classList.toggle("color__dark");
  }
</script>

<Router {url}>
  <Route path="/"><HomePage /></Route>
  <Route path="/beernuts"><BeerNuts /></Route>
  <Route path="/tag"><Tag /></Route>
  <Route path="/pixo"><Pixo /></Route>
  <Route path="/saferillinois"><SaferIllinois /></Route>
  <Route path="/aptech"><Aptech /></Route>
  <Route path="/interactivecomponent"><InteractiveComponent /></Route>
</Router>

<style lang="scss">
  @import "./style/global.scss";
  @import "./style/theme.scss";

  .html {
    scroll-behavior: smooth;

    @media screen and (prefers-reduced-motion: reduce) {
      html {
        scroll-behavior: auto;
      }
    }
  }

  :global(body.color__light) {
    @include LightTheme;
  }
  :global(body.color__dark) {
    @include DarkTheme;
  }
  :global(body) {
    background-color: $background-primary;
  }
  :global(h1, h2, h3, h4, h5, h6, p, span, body) {
    color: $text-primary;
  }
</style>
