<script>
import CardList from "./components/CardList.vue";
import AppHeader from "./components/AppHeader.vue";

export default {
  components: {
    CardList,
    AppHeader,
  },
};
</script>

<template>
  <AppHeader />
  <main>
    <CardList />
  </main>
</template>

<style lang="scss">
@use "./assets/scss/style.scss";
</style>
