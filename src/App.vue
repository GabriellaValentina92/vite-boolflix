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
};
</script>

<template>
  <searchHeader />
  <mainShows />
</template>

<style lang="scss">
@use "./assets/style/general.scss";
</style>
