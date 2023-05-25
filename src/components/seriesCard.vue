<script>
export default {
  props: {
    seriesCard: Object,
  },

  methods: {
    convertNumber() {
      const vote = this.seriesCard.vote_average / 2;
      return Math.round(vote);
    },
  },
};
</script>

<template>
  <div class="series">
    <h3>{{ seriesCard.name }}</h3>
    <h4>{{ seriesCard.original_name }}</h4>
    <h5>{{ seriesCard.original_language }}</h5>
    <div>voto: {{ convertNumber() }}</div>
    <img
      :src="'https://image.tmdb.org/t/p/w154' + seriesCard.poster_path"
      alt="Immagine non disponibile = ("
    />
  </div>
</template>

<style lang="scss" scoped>
.series {
  text-align: center;
  background-color: black;
  color: white;
  border: 4px solid white;
  margin-top: 4px;
}
</style>
