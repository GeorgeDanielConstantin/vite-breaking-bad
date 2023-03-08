<script>
import axios from "axios";

export default {
  data() {
    return {
      cards: [],
    };
  },

  created() {
    axios
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=0")
      .then((response) => {
        this.cards = response.data.data;
      });
  },
};
</script>

<template>
  <section>
    <div class="container p-4 text-center">
      <div class="row row-cols-5 gy-3">
        <div class="col" v-for="card in cards">
          <img :src="card.card_images.image_url" class="img-fluid" alt="" />
          <h3>{{ card.name }}</h3>

          <p>{{ card.archetype }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.container {
  background-color: white;
}

.col {
  height: 200px;
  background-color: #d48f38;
}
h3 {
  color: white;
}
</style>
