<script>
import movieComponent from "./movieComponent.vue";
import seriesComponent from "./seriesComponent.vue";
import { store } from "../store";

export default {
  data() {
    return {
      store,
    };
  },

  components: {
    movieComponent,
    seriesComponent,
  },
};
</script>
<template>
  <movieComponent />
  <seriesComponent />
</template>

<style lang="scss" scoped></style>
