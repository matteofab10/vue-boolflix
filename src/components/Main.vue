<template>
  <div class="main-background">
    <div class="container cards-container">
        <Cards />
    </div>
  </div>
</template>

<script>

import axios from "axios";
import Cards from './Cards.vue';


export default {
  name: "Main",
  components: {
    Cards,
  },
  data(){
    return{
      Cards: [],
      apiUrl: "https://api.themoviedb.org/3/search/movie?"
    }
  },
  // props: {
    
  // },
  // computed: {
    
  // },
  methods:{
    getApi(){
      axios.get(this.apiUrl)
        .then( r => {
          this.cards = r.data;
        })
        .catch( e => {
          console.log(e);
        })
    },
  },
    mounted(){
    this.getApi();
  }
}
</script>

<style lang="scss">
  @import "../assets/style/vars.scss";

  .main-background {
    min-height: calc(100vh - 60px);
    background-color: grey;
    color: white;
    .cards-container {
      display: flex;
      flex-wrap: wrap;
      padding-top: 50px;
    }
  }

</style>