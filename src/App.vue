<template>
  <div id="app">
    <header-section @search="searchAll" />
    <main-component :filterAll="filterAll" />
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
      filterAll: [],
    };
  },
  methods: {
    searchAll(keyWord) {
      
        axios
          .get(
            `https://api.themoviedb.org/3/search/movie?&query=${keyWord}&api_key=9a08180013f02b9f6ba384978c7e712b&language=it`
            
          )
          .then((response) => {
            this.filterAll = response.data.results;
          });
      
        axios
          .get(
            `https://api.themoviedb.org/3/search/tv?&query=${keyWord}&api_key=9a08180013f02b9f6ba384978c7e712b&language=it`
            
          )
          .then((response) => {
            this.filterAll = response.data.results;
          });
      }


    },
};
</script>

<style lang="scss">
@import "./style/general.scss"; //scss generale -- Bootsrap -- Fontawesome
</style>