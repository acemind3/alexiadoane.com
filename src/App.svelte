<script lang="ts">
  import { Router, Route } from "svelte-routing";

  import HomePage from "./pages/home/HomePage.svelte";
  import BeerNuts from "./pages/portfolio/BeerNuts.svelte";
  import Tag from "./pages/portfolio/Tag.svelte";
  import Pixo from "./pages/portfolio/Pixo.svelte";

  export let url = window.location.pathname;
</script>

<Router {url}>
  <Route path="/"><HomePage /></Route>
  <Route path="/beernuts"><BeerNuts /></Route>
  <Route path="/tag"><Tag /></Route>
  <Route path="/pixo"><Pixo /></Route>
</Router>
