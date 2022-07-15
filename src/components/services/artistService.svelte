<script lang="ts" context="module">
  import { ArtistStore } from "../../artistStore";

  import { LoadingStore } from "../../LoadingStore";

  export const getArtist = async (artistName: string) => {
    LoadingStore.set(true);

    fetch(`https://rest.bandsintown.com/artists/${artistName}?app_id=test`)
      .then((response) => response.json())
      .then((data) => {
        ArtistStore.update(() => {
          LoadingStore.set(false);
          return data;
        });
      });
  };
</script>
