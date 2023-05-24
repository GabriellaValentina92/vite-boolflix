<script>
import { store } from "../store";

export default {
  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <div class="container">
    <h1>Boolflix</h1>
    <div class="search">
      <input type="text" />
      <button>Search</button>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1rem;
  background-color: rgb(51, 187, 128);

  h1 {
    color: white;
    font-weight: 900;
  }

  .search input {
    margin-right: 0.8rem;
    height: 1.5rem;
    width: 20rem;
  }

  .search button {
    height: 1.5rem;
    color: rgb(248, 135, 6);
  }
}
</style>
