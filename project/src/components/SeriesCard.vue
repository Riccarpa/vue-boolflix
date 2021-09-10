<template>
  <div class="card">
    <ul>
      <li>TITOLO: {{ serie.name }}</li>
      <li>TITOLO ORIGINALE: {{ serie.original_name }}</li>
      <li>
        LINGUA:
        <img :src="flagRender()" :alt="serie.original_language" />
      </li>
      <li>VOTO: {{ serie.vote_average }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: ["serie"],
  methods: {
    flagRender() {
      if (this.serie.original_language === "it") {
        return require("../images/it.png");
      } else if (this.serie.original_language === "en") {
        return require("../images/en.png");
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.card {
  margin: 2rem;
  img {
    height: 15px;
  }
}
</style>
