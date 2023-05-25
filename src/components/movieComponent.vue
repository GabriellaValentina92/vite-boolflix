<script>
import movieCard from "./movieCard.vue";
import { store } from "../store";

export default {
  data() {
    return {
      store,
    };
  },

  components: {
    movieCard,
  },
};
</script>

<template>
  <h1>Elenco dei film disponibili:</h1>
  <div class="container">
    <movieCard
      v-for="card in store.entertainmentList"
      :key="card.id"
      :movieCards="card"
      class="card"
    />
  </div>
</template>

<style lang="scss" scoped>
.container {
  display: flex;
  flex-wrap: wrap;

  .card {
    flex: 0 0 20%;
  }
}
</style>
