<template>
  <div>
    <Header @foundFilm="foundFilm" />
    <Main :films="films" />
  </div>
  
</template>

<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import axios from "axios";

export default {
  name: 'App',
  components: {
    Header,
    Main,
  },
  data(){
    return{
      films: [],
      apiURL: 'https://api.themoviedb.org/3/search/movie?',
      apiKey: '6c09bd2152ffacc0fcf183bbf3e46424',
    }
  },
  methods:{
    foundFilm(input){
      axios.get(`${this.apiURL}api_key=${this.apiKey}&query=${input}&language=it-IT`)
        .then((response) =>{
          this.films = response.data.results;
          console.log(this.films);
        })
        .catch((error) =>{
          console.log(error);
        })
    }
  }
}
</script>

<style lang="scss">

@import "./assets/style/vars.scss";
@import "./assets/style/utilities.scss";
@import "./assets/style/generals.scss";

</style>

