<template>
  <main>
    <div class="container">
      <div v-for="film in films" :key="film.id" class="film-card">
        <ol>
          <li>Titolo: {{film.title}}</li>
          <li>Titolo originale: {{film.original_title}}</li>
          <li>Lingua originale: {{film.original_language}}</li>
          <li>Voto: {{film.vote_average}}</li>
        </ol>
      </div>
    </div>
  </main>
</template>

<script>

export default {
  name: "Main",
  data() {
    return {

    }
  },
  props: {
    films: Array,
  },
}

</script>

<style lang="scss">
  @import "../assets/style/vars.scss";

  main {
    min-height: calc(100vh - 60px);
    background-color: grey;
    color: white;
    overflow: auto;
    .container {
      padding-top: 50px;
      display: flex;
      flex-wrap: wrap;
    }
    .film-card {
      width: 350px;
      background-color: red;
      color: white;
      margin: 0 20px 10px 0;
    }
  }

</style>