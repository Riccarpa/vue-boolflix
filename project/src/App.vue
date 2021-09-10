<template>
  <div id="app">
    <Header @search="ApiCall" />
    <main>
      <Library :moovies="moovies" />
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
      apiKey: "?api_key=e99307154c6dfb0b4750f6603256716d",
      moovies: [],
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
    },
  },
  created() {
    this.ApiCall();
  },
};
</script>

<style lang="scss">
@import "assets/scss/_style.scss";
</style>
