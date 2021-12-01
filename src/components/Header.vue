<template>
  <header>
    <div class="logo-boolflix">
      boolflix 
    </div>

    <div class="search-container">
    <form action="/action_page.php">
      <input type="text" placeholder="Cerca.." name="search">
      <button type="submit">Cerca</button>
    </form>
  </div>
  </header>
</template>

<script>

export default {
  name: "Header",
  props: {

  },
  data(){
    return {
      
    }
  },
}
</script>

<style lang="scss">
  @import "../assets/style/vars.scss";

  header {
    height: 60px;
    background-color: black;
    display: flex;
    justify-content: space-between;
    align-items: center;
    .logo-boolflix {
      color: red;
      text-transform: uppercase;
      font-size: 40px;
      margin-left: 15px;
      cursor: pointer;
    }
    // img {
    //   width: 100%;
    //   margin-left: 15px;
    //   cursor: pointer;
    // }
    .search-container {
      margin-right: 15px;
    }
  }
  

</style>