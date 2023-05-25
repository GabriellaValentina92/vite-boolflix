<script>
export default {
  props: {
    movieCards: Object,
  },

  methods: {
    convertNumber() {
      const vote = this.movieCards.vote_average / 2;
      return Math.round(vote);
    },
  },
};
</script>

<template>
  <div class="movies">
    <h3>{{ movieCards.title }}</h3>
    <h4>{{ movieCards.original_title }}</h4>
    <h5>{{ movieCards.original_language }}</h5>
    <div>{{ convertNumber() }}</div>
    <img src="" alt="" />
  </div>
</template>

<style lang="scss" scoped>
.movies {
  background-color: black;
  color: white;
  border: 4px solid white;
  margin-top: 4px;
}
</style>
