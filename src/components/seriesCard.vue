<script>
import LangFlag from "vue-lang-code-flags/LangFlag.vue";
import { VueFlip } from "vue-flip";
export default {
  components: {
    LangFlag,
    "vue-flip": VueFlip,
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
          :src="'https://image.tmdb.org/t/p/w154' + seriesCard.poster_path"
          alt="Immagine non disponibile = ("
        />
      </div>
    </template>
    <template v-slot:back>
      <div class="series">
        <h3>{{ seriesCard.name }}</h3>
        <h4>{{ seriesCard.original_name }}</h4>
        <h5>
          <LangFlag :iso="seriesCard.original_language" :squared="false" />
        </h5>
        <span class="lang-text">{{ seriesCard.original_language }}</span>
        <div>voto: {{ convertNumber() }}</div>
      </div>
    </template>
  </vue-flip>
</template>

<style lang="scss" scoped>
.frontImg {
  .frontImg img {
    display: block;
    width: 100%;
    height: 200px;
    padding: 0.7rem;
  }
}
.series {
  width: 200px;
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
