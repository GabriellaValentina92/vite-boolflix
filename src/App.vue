<script>
import searchHeader from "./components/searchHeader.vue";
import mainShows from "./components/mainShows.vue";
import axios from "axios";
import { store } from "./store";

export default {
  data() {
    return {
      store,
    };
  },

  components: {
    searchHeader,
    mainShows,
  },

  methods: {
    datafromApi(searchMovie) {
      axios
        .get("https://api.themoviedb.org/3/search/movie", {
          params: {
            query: searchMovie,
            include_adult: "false",
            language: "it-IT",
            api_key: "2daf3b78dc2479cf32ccffe1df62ec94",
          },
        })
        .then(
          (response) => (this.store.entertainmentList = response.data.results)
        );

      axios
        .get("https://api.themoviedb.org/3/search/tv", {
          params: {
            query: searchMovie,
            include_adult: "false",
            language: "it-IT",
            api_key: "2daf3b78dc2479cf32ccffe1df62ec94",
          },
        })
        .then((response) => (this.store.arrSeries = response.data.results));
    },
  },
};
</script>

<template>
  <searchHeader @performSearch="datafromApi" />
  <mainShows />
</template>

<style lang="scss">
@use "./assets/style/general.scss";
</style>
