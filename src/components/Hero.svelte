<script>
  import { ArtistStore } from "../../stores";
</script>

<div class="container">
  <div
    class="coverImage"
    style="background-image: url({$ArtistStore?.image_url});"
  />
  <div class="avatar">
    <img src={$ArtistStore?.thumb_url} alt={$ArtistStore?.name} />
  </div>

  <div class="title">
    <h1>{$ArtistStore?.name}</h1>
    <h3>
      {`${$ArtistStore?.tracker_count} Followers . ${$ArtistStore?.upcoming_event_count} Upcoming Concerts`}
    </h3>
  </div>
</div>

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
</style>
