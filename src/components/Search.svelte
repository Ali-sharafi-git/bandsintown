<script>
  import { getArtist } from "./services/artistService.svelte";
  let searchString = "";

  const onKeyPress = (e) => {
    if (e.charCode === 13) {
      getArtist(searchString);
    }
  };
</script>

<div class="container">
  <div class="inputContainer">
    <img src="images/loupe.svg" alt />
    <input
      bind:value={searchString}
      type="text"
      placeholder="Search for artists, concerts, venues and festivals"
      on:keypress={onKeyPress}
    />
  </div>
</div>

<style>
  .container {
    margin-right: 42px;
    max-width: 600px;
    display: inline-block;
    width: 40%;
  }
  .inputContainer {
    display: inline-block;
    position: relative;
    width: 100%;
  }
  img {
    position: absolute;
    left: 13px;
    top: 18px;
    z-index: 50;
  }
  input {
    position: relative;
    font-size: 16px;
    color: #8f8f8f;
    font-weight: 500;
    height: 47px;
    width: 100%;
    border: solid 1px #cdcdcd;
    border-radius: 3px;
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
    box-shadow: 0 1px 3px 0 rgb(0 0 0 / 8%);
    padding: 1px 10px 0px 37px;
    outline: none;
    box-sizing: border-box;
    position: relative;
    top: 2px;
  }
</style>
