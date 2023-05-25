<script>
export default {
  props: {
    movieCards: Object,
  },
};
</script>

<template>
  <div class="movies">
    <h3>{{ movieCards.title }}</h3>
    <h4>{{ movieCards.original_title }}</h4>
    <h5>{{ movieCards.original_language }}</h5>
    <div>{{ movieCards.vote_average }}</div>
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
