<template>
  <div class="card">
    <img class="card-bg" :src="coverRender()" alt="" />
    <ul>
      <li>TITOLO: {{ moovie.title }}</li>
      <li>TITOLO ORIGINALE: {{ moovie.original_title }}</li>
      <li>
        LINGUA:
        <img
          class="flag"
          :src="flagRender()"
          v-text="flagRender()"
          :alt="moovie.original_language"
        />
      </li>
      <li>
        VOTO:<i
          v-for="(item, index) in voteRender"
          :key="index"
          :class="item === 'blackStar' ? 'far fa-star' : 'fas fa-star'"
        ></i>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: ["moovie"],

  computed: {
    voteRender() {
      const vote = Math.ceil(this.moovie.vote_average / 2);
      const stars = [];
      const blackStars = [];

      for (var i = 0; i <= vote - 1; i++) {
        stars.push("star");
      }
      const totalStars = [...stars, ...blackStars];
      while (totalStars.length < 5) {
        totalStars.push("blackStar");
      }

      return totalStars;
    },
  },
  methods: {
    flagRender() {
      if (this.moovie.original_language === "it") {
        return require("../images/it.png");
      } else if (this.moovie.original_language === "en") {
        return require("../images/en.png");
      }
    },
    coverRender() {
      const baseUri = "https://image.tmdb.org/t/p/w342";

      if (!this.moovie.poster_path) {
        return require("@/images/poster-placeholder.png");
      }
      return `${baseUri}${this.moovie.poster_path}`;
    },
  },
};
</script>
