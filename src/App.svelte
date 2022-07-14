<script>
  import { onMount } from "svelte";
  import { ArtistStore } from "../stores";
  import Header from "./components/Header.svelte";
  import Hero from "./components/Hero.svelte";

  onMount(async () => {
    fetch("https://rest.bandsintown.com/artists/colab?app_id=test")
      .then((response) => response.json())
      .then((data) => {
        ArtistStore.update(() => {
          return data;
        });
        console.log("data", data);
      });
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
