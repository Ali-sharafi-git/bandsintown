<script lang="ts">
  import { onMount } from "svelte";

  import { getArtist } from "./components/services/artistService.svelte";
  import Header from "./components/Header.svelte";
  import Hero from "./components/Hero.svelte";

  onMount(async () => {
    // default artist
    await getArtist("Colab");
  });
</script>

<div class="container">
  <Header />
  <div class="content">
    <Hero />
  </div>
</div>

<style>
  .container {
    display: block;
  }
  .content {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin: 20px 0;
  }
</style>
