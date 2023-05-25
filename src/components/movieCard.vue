<script>
export default {
  props: {
    movieCards: Object,
  },
};
</script>

<template>
  <div class="movies">
    <h1>{{ movieCards.title }}</h1>
    <h2>{{ movieCards.original_title }}</h2>
    <h3>{{ movieCards.original_language }}</h3>
    <div>{{ movieCards.vote_average }}</div>
    <img src="" alt="" />
  </div>
</template>

<style lang="scss" scoped></style>
