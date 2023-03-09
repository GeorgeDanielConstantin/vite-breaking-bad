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
      <div class="row row-cols-5 g-4">
        <div class="col my-5" v-for="card in cards">
          <div>
            <img
              :src="card.card_images[0].image_url"
              class="img-fluid"
              alt=""
            />
            <h5>{{ card.name }}</h5>

            <p>{{ card.type }}</p>
          </div>
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
}

.col > div {
  background-color: #d48f38;
  width: 150px;
}
h5 {
  color: white;
}

.col img {
  height: 200px;
  width: 150px;
}
</style>
