<script>
  import { onMount } from "svelte";

  import Home from "../containers/home.svelte";
  import Usps from "../containers/usp.svelte";

  let home;
  let usps;

  function hashHandler() {
    const currentHash = window.location.hash.split("#")[1];
    switch (currentHash) {
      case "usps":
        window.scrollTo({
          top: window.screen.availHeight,
          behavior: "smooth",
        });
        break;
      case "home":
      default:
        window.scrollTo({
          top: 0,
          behavior: "smooth",
        });
        break;
    }
  }

  onMount(() => {
    window.addEventListener("hashchange", hashHandler, false);
    window.addEventListener('resize', hashHandler, false);
    hashHandler();
  });
</script>

<main>
  <Home bind:this={home} />
  <Usps bind:this={usps} />
</main>

<style>
  main {
    position: relative;
    max-width: 56em;
    margin: 0 auto;
  }
</style>
