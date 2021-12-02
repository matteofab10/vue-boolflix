<template>
  <div>
    <Header @movieFound="movieFound" />
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
      apiParams: {
        api_key: '6c09bd2152ffacc0fcf183bbf3e46424',
        language: 'it-IT',
        query: ''
      }
    }
  },
  methods:{
    movieFound(input){
      this.apiParams.query = input;

      axios.get(this.apiURL, {params: this.apiParams})
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

