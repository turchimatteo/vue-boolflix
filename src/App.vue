<template>
  <div id="app">
    <Header @userSearch="search" />
    <Main :movieList="movies" :seriesList="series" />
  </div>
</template>

<script>
import axios from 'axios';

import Header from "./components/Header.vue";
import Main from "./components/Main.vue";

export default {
  name: "App",
  components: {
    Header,
    Main,
  },
  data: function() {
    return {
      queryValue: '',
      apiKey: 'fd8cc687d74cb59ac7f263f9d2edb2ab',
      movies: [],
      series: [],
    }
  },
  methods: {
    search: function(userString) {
      this.queryValue = userString;
      this.getMovies();
      this.getSeries();
    },
    getMovies: function() {
      axios.get(
        'https://api.themoviedb.org/3/search/movie',
        {
          params: {
            api_key: this.apiKey,
            query: this.queryValue,
          }
        }
      ).then((response) => {
        console.log(response);
        this.movies = response.data.results;
      });
    },
    getSeries: function() {
      axios.get(
        'https://api.themoviedb.org/3/search/tv',
        {
          params: {
            api_key: this.apiKey,
            query: this.queryValue,
          }
        }
      ).then((response) => {
        console.log(response);
        this.series = response.data.results;
      });
    }
  },
};
</script>

<style lang="scss">

</style>
