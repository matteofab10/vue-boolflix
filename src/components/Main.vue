<template>
  <main>
    <div v-for="film in films" :key="film.id" class="container">
      <ul>
        <li>Titolo: {{film.title}}</li>
        <li>Titolo originale: {{film.original_title}}</li>
        <li>Lingua originale{{film.original_language}}</li>
        <li>Voto: {{film.vote_average}}</li>
      </ul>
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
    .container {
      display: flex;
      flex-wrap: wrap;
      width: 300px;
      padding-top: 50px;
    }
    ul {
      color: white;
    }
  }

</style>