<template>
  <header>
    <div class="logo-boolflix">
      <h1>boolflix</h1>
    </div>

    <div class="search-container">
      <input v-model="filmToSearch" @keyup.enter="searchFilm" type="text" placeholder="Cerca.." name="search">
      <button @click="searchFilm" type="submit">Cerca</button>
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
      font-size: 20px;
      margin-left: 15px;
      cursor: pointer;
    }
    .search-container {
      margin-right: 15px;
    }
  }
  

</style>