<script>
  import Search from "./Search.svelte";
</script>

<div class="container">
  <header>
    <img src="images/logo.svg" alt="bands in town" />
    <Search />

    <div class="actions">
      <a href="#"> Sign Up </a>
      <a href="#"> Log In </a>
    </div>
  </header>
</div>

<style>
  .container {
    position: sticky;
    top: 0;
  }
  header {
    border-bottom: 1px solid #cdcdcd;
    background-color: #ffffff;
    height: 75px;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    box-sizing: border-box;
  }
  img {
    text-align: left;
    margin-left: 15px;
    margin: 2px 10px 0px;
    display: inline-block;
    white-space: nowrap;
  }

  .actions a {
    display: inline-block;
    margin: 0px 10px;
    white-space: nowrap;
    cursor: pointer;
    vertical-align: middle;
    font-weight: bold;
    color: #08c3ba;
    text-decoration: none;
    padding-right: 20px;
    font-size: large;
  }

  @media (max-width: 768px) {
    header {
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }
    img {
      width: 100%;
    }
  }
</style>
