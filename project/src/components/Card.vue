<template>
  <div class="card">
    <ul>
      <li>TITOLO: {{ moovie.title }}</li>
      <li>TITOLO ORIGINALE: {{ moovie.original_title }}</li>
      <li>
        LINGUA:
        <img
          :src="flagRender()"
          v-text="flagRender()"
          :alt="moovie.original_language"
        />
      </li>
      <li>VOTO: {{ moovie.vote_average }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: ["moovie"],
  methods: {
    flagRender() {
      if (this.moovie.original_language === "it") {
        return require("../images/it.png");
      } else if (this.moovie.original_language === "en") {
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
