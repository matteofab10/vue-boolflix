<template>
  <main>
    <div class="container">
      <h2>film</h2>
      <div class="container-card">
        <Card v-for="film in films" :key="film.id"
          :image="`${imageUrl}${film.poster_path}`"
          :title="film.title"
          :originalTitle="film.original_title"
          :originalLanguage="film.original_language"
          :voteAverage="film.vote_average"
        />
      </div>
      <h2>series</h2>
      <div class="container-card">
        <Card v-for="series in tvSeries" :key="series.id"
          :image="`${imageUrl}${series.poster_path}`"
          :title="series.name"
          :originalTitle="series.original_name"
          :originalLanguage="series.original_language"
          :voteAverage="series.vote_average"
        />
      </div>
    </div>
  </main>
</template>

<script>
import Card from './Card.vue';

export default {
  name: "Main",
  components: {
    Card,
  },

  data() {
    return {
      imageUrl: 'https://image.tmdb.org/t/p/w342',
    }
  },
  props: {
    films: Array,
    tvSeries: Array,
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
      flex-direction: column;
    }
    h2 {
      text-transform: uppercase;
    }
    .container-card {
      margin: 0 20px 10px 0;
    }
  }

</style>