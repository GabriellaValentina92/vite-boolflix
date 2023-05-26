<script>
import LangFlag from "vue-lang-code-flags/LangFlag.vue";
export default {
  components: {
    LangFlag,
  },

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
    <h2>{{ movieCards.title }}</h2>
    <h4>{{ movieCards.original_title }}</h4>
    <h5><LangFlag :iso="movieCards.original_language" :squared="false" /></h5>
    <span class="text-lang">{{ movieCards.original_language }}</span>
    <div>voto: {{ convertNumber() }}</div>
    <img
      :src="'https://image.tmdb.org/t/p/w342' + movieCards.poster_path"
      alt="imagine non disponibile = ("
    />
  </div>
</template>

<style lang="scss" scoped>
.movies {
  width: 400px;
  text-align: center;
  background-color: black;
  color: white;
  border: 4px solid white;
  margin-top: 4px;

  h2,
  h4,
  h5,
  div {
    padding: 0.6rem;
  }

  img {
    width: 100%;
    padding: 0.7rem;
  }
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
