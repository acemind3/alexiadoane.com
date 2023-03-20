<script>
  import SectionTitle from "../lib/SectionTitle.svelte";
  import TwoColumnContentBlock from "./TwoColumnContentBlock.svelte";

  const hobbies = [
    "Learning to play cello",
    "Making lofi beats",
    "Watercolor sketches",
    "Bird watching",
    "Skateboarding",
  ];
</script>

<div id="about" />
<TwoColumnContentBlock
  leftSectionTitle="about me"
  rightSectionTitle="hobbies"
  rightSectionItems={hobbies}
>
  <p slot="left">
    I'm an all around optimistic artist who likes anything and everything
    design. When I'm not off perfecting my craft, I'm a musician, video gamer,
    board game enthusiast, and adventurer.
  </p>
</TwoColumnContentBlock>

<style>
  #about {
    scroll-behavior: smooth;
  }
</style>
