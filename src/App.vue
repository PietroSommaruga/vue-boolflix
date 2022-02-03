<template>
  <div id="app">
    <header-section @search="searchMovie" />
    <main-component :moviesProp="getMovies" />
  </div>
</template>

<script>
import axios from "axios";
import HeaderSection from "./components/HeaderSection.vue";
import MainComponent from "./components/MainComponent.vue";
export default {
  name: "App",
  components: { 
    HeaderSection, 
    MainComponent, 
    },
  data() {
    return {
      getMovies: [],
    };
  },
  methods: {
    searchMovie(movieName) {
      if (movieName === "") {
        this.getMovies = [];
      } else {
        axios
          .get(
            `https://api.themoviedb.org/3/search/movie?&query=${movieName}&api_key=9a08180013f02b9f6ba384978c7e712b&language=it`
            
          )
          .then((response) => {
            this.getMovies = response.data.results;
          });
      }
    },
  },
};
</script>

<style lang="scss">
@import "./style/main.scss"; //scss generale -- Bootsrap
</style>

