<script>
import LangFlag from "vue-lang-code-flags/LangFlag.vue";
import { VueFlip } from "vue-flip";
export default {
  components: {
    LangFlag,
    "vue-flip": VueFlip,
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
  <vue-flip
    active-click=""
    :active-hover="true"
    transition="2s"
    width="342px"
    height="300px"
  >
    <template v-slot:front>
      <div class="frontImg">
        <img
          :src="'https://image.tmdb.org/t/p/w342' + movieCards.poster_path"
          alt="imagine non disponibile = ("
        />
      </div>
    </template>
    <template v-slot:back>
      <div class="movies">
        <h2>{{ movieCards.title }}</h2>
        <h4>{{ movieCards.original_title }}</h4>
        <h5>
          <LangFlag :iso="movieCards.original_language" :squared="false" />
        </h5>
        <span class="text-lang">{{ movieCards.original_language }}</span>
        <div>voto: {{ convertNumber() }}</div>
      </div>
    </template>
  </vue-flip>
</template>

<!-- <font-awesome-icon :icon="['far', 'star']" /> -->

<style lang="scss" scoped>
.frontImg {
  .frontImg img {
    display: block;
    width: 100%;
    height: 200px;
    padding: 0.7rem;
  }
}
.movies {
  width: 342px;
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
