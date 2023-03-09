<script>
export default {
  data() {
    return {
      cardTypes: [
        "Effect Monster",
        "Flip Effect Monster",
        "Flip Tuner Effect Monster",
        "Gemini Monster",
        "Normal Monster",
        "Normal Tuner Monster",
        "Pendulum Effect Monster",
        "Pendulum Effect Ritual Monster",
        "Pendulum Flip Effect Monster",
        "Pendulum Normal Monster",
        "Pendulum Tuner Effect Monster",
        "Ritual Effect Monster",
        "Ritual Monster",
        "Spell Card",
        "Spirit Monster",
        "Toon Monster",
        "Trap Card",
        "Tuner Monster",
        "Union Effect Monster",
        "Fusion Monster",
        "Link Monster",
        "Pendulum Effect Fusion Monster",
        "Synchro Monster",
        "Synchro Pendulum Effect Monster",
        "Synchro Tuner Monster",
        "XYZ Monster",
        "XYZ Pendulum Effect Monster",
        "Skill Card",
        "Token",
      ],
    };
  },
  emits: ["invio-dati"],

  methods: {
    selectedType() {
      this.$emit("invio-dati", this.searchedType);
    },
  },
};
</script>

<template>
  <div class="container p-4">
    <div class="input-group" @submit.prevent="">
      <select
        class="form-select"
        id="inputGroupSelect04"
        aria-label="Example select with button addon"
        v-model="searchedType"
        @change="if (searchedType) selectedType();"
      >
        <option v-for="cardType in cardTypes">{{ cardType }}</option>
      </select>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
