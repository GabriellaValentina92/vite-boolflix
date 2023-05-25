<script>
export default {
  props: {
    seriesCard: Object,
  },
};
</script>

<template>
  <div class="series">
    <h3>{{ seriesCard.name }}</h3>
    <h4>{{ seriesCard.original_name }}</h4>
    <h5>{{ seriesCard.original_language }}</h5>
    <div>{{ seriesCard.vote_average }}</div>
    <img src="" alt="" />
  </div>
</template>

<style lang="scss" scoped>
.series {
  background-color: black;
  color: white;
  border: 4px solid white;
  margin-top: 4px;
}
</style>
