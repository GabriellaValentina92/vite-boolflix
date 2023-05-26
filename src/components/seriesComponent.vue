<script>
import seriesCard from "./seriesCard.vue";
import { store } from "../store";

export default {
  data() {
    return {
      store,
    };
  },

  components: {
    seriesCard,
  },
};
</script>

<template>
  <h1>Elenco delle serie Tv disponibili:</h1>
  <div class="container">
    <seriesCard
      v-for="series in store.arrSeries"
      :key="series.id"
      :seriesCard="series"
      class="card"
    />
  </div>
</template>

<style lang="scss" scoped>
h1 {
  margin-top: 3rem;
}
.container {
  display: flex;
  flex-wrap: wrap;

  .card {
    flex: 0 0 30%;
  }
}
</style>
