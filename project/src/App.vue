<template>
  <div id="app">
    <Header @search="ApiCall" />
    <main>
      <Library :moovies="moovies" :series="series" />
    </main>
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import Library from "@/components/Library.vue";
import axios from "axios";
export default {
  name: "App",
  components: {
    Header,
    Library,
  },
  data() {
    return {
      baseUri: "https://api.themoviedb.org/3/search/movie",
      baseSeriesUri: "https://api.themoviedb.org/3/search/tv",
      apiKey: "?api_key=0027d52b7964d653987c8a470eaa97d8",
      moovies: [],
      series: [],
    };
  },
  computed: {},
  methods: {
    ApiCall(query) {
      if (query) {
        axios
          .get(`${this.baseUri}${this.apiKey}&query=${query}`)
          .then((res) => {
            this.moovies = res.data.results;
          });
      }
      if (query) {
        axios
          .get(`${this.baseSeriesUri}${this.apiKey}&query=${query}`)
          .then((res) => {
            this.series = res.data.results;
          });
      }
    },
  },
};
</script>

<style lang="scss">
@import "assets/scss/_style.scss";
</style>
