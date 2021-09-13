<template>
  <div class="card">
    <img class="card-bg" :src="coverRender()" alt="" />
    <ul>
      <li>TITOLO: {{ serie.name }}</li>
      <li>TITOLO ORIGINALE: {{ serie.original_name }}</li>
      <li>
        LINGUA:
        <img class="flag" :src="flagRender()" :alt="serie.original_language" />
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
  name: "SeriesCard",
  props: ["serie"],
  computed: {
    voteRender() {
      const vote = Math.ceil(this.serie.vote_average / 2);
      const stars = [];

      for (var i = 0; i <= vote - 1; i++) {
        stars.push("star");
      }
      const totalStars = [...stars];
      while (totalStars.length < 5) {
        totalStars.push("blackStar");
      }

      return totalStars;
    },
  },
  methods: {
    flagRender() {
      if (this.serie.original_language === "it") {
        return require("../images/it.png");
      } else if (this.serie.original_language === "en") {
        return require("../images/en.png");
      }
    },
    coverRender() {
      const baseUri = "https://image.tmdb.org/t/p/w342";

      if (!this.serie.poster_path) {
        return require("@/images/poster-placeholder.png");
      }
      return `${baseUri}${this.serie.poster_path}`;
    },
  },
};
</script>
