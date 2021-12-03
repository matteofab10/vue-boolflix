<template>
  <header>
    <div class="logo-boolflix">
      <img src="../assets/img/boolflix-logo.png" alt="logo-boolflix">
    </div>

    <div class="header-right">
      <div class="search-container">
        <input v-model="filmToSearch" @keyup.enter="searchFilm" type="text" placeholder="Cerca.." name="search">
        <button @click="searchFilm" type="submit">Cerca</button>
      </div>

      <!-- <select v-model="type" class="type-bar" aria-label="Default select example">
        <option value="all" selected>All</option>
        <option value="films">Films</option>
        <option value="series">Series</option>
      </select> -->
    </div>
  </header>
</template>

<script>

export default {
  name: "Header",
  
  data(){
    return {
      filmToSearch: '',
    }
  },
  methods: {
    searchFilm(){
      this.$emit('movieFound', this.filmToSearch)
    }
  }
}
</script>

<style lang="scss" scoped>
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
      font-size: 20px;
      margin-left: 15px;
      cursor: pointer;
      img {
        width: 150px;
        height: 100%;
        vertical-align: middle;
      }
    }
    .search-container {
      margin-right: 15px;
    }
    .type-bar {
      margin-right: 15px;
    }
    .header-right {
      display: flex;
      justify-content: flex-end;
    }
  }
  

</style>