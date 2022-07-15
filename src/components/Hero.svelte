<script lang="ts">
  import { ArtistStore } from "../artistStore";
  import { LoadingStore } from "../LoadingStore";

  import Button from "./ui/Button.svelte";
  import type { Artist } from "./services/types/artistModel";

  $: artist = $ArtistStore as Artist;
  $: loading = $LoadingStore as boolean;
  // $: {
  //   console.log("artist", artist);
  // }
</script>

{#if loading}
  <h2>Loading ...</h2>
{:else if !artist}
  <h1>Artist not found</h1>
{:else}
  <div class="container">
    <div
      class="coverImage"
      style="background-image: url({artist?.image_url});"
    />
    <div class="avatar">
      <img src={artist?.thumb_url} alt={artist?.name} />
    </div>

    <div class="title">
      <h1>{artist?.name}</h1>
      <h3>
        {`${Number(artist?.tracker_count).toLocaleString()} Followers . ${
          artist?.upcoming_event_count
        } Upcoming Concerts`}
      </h3>
    </div>

    <div class="follow">
      <Button type="button">Follow</Button>
    </div>
  </div>
{/if}

<style>
  .container {
    position: relative;
    min-height: 250px;
    width: 70%;
    margin: auto;
    border: 1px solid #ccc;
    border-radius: 4px;
    overflow: hidden;
  }
  .coverImage {
    min-height: 250px;
    background-repeat: no-repeat;
    background-position: top;
    background-size: cover;
    filter: blur(8px);
    z-index: 0;
  }
  .avatar {
    position: absolute;
    top: 50%;
    left: 10%;
    transform: translate(-50%, -50%);
  }
  img {
    border-radius: 50%;
    width: 150px;
  }
  .title {
    line-height: 10px;
    position: absolute;
    top: 50%;
    left: 40%;
    transform: translate(-50%, -50%);
    color: #fff;
  }

  .follow {
    position: absolute;
    top: 50%;
    left: 85%;
    transform: translate(-50%, -50%);
  }
</style>
