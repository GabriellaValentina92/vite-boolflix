<script>
import LangFlag from "vue-lang-code-flags/LangFlag.vue";
export default {
  components: {
    LangFlag,
  },

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
    <h5><LangFlag :iso="seriesCard.original_language" :squared="false" /></h5>
    <span class="lang-text">{{ seriesCard.original_language }}</span>
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
.lang-text {
  display: none;
}
.flag-icon-indefined {
  display: none;
}

.flag-icon-indefined + .lang-text {
  display: inline;
}
</style>
