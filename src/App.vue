<script>
import CardList from "./components/CardList.vue";
import AppHeader from "./components/AppHeader.vue";
import SearchBar from "./components/SearchBar.vue";

export default {
  components: {
    CardList,
    AppHeader,
    SearchBar,
  },

  methods: {},
};
</script>

<template>
  <AppHeader />
  <main>
    <SearchBar />
    <CardList />
  </main>
</template>

<style lang="scss">
@use "./assets/scss/style.scss";
</style>
