<template>
  <header>
    <div class="container">
      <figure id="logo">
        <img src="@/assets/logo.png" alt="logo" />
        <figcaption>Boolflix</figcaption>
      </figure>
      <div id="search">
        <input v-model="query" type="text" placeholder="Cerca..." />
        <button @click="emitSearch">Vai</button>
        <!-- <button @click="reset">Reset</button> -->
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      query: "",
    };
  },
  methods: {
    emitSearch() {
      if (this.query.trim()) {
        this.$emit("search", this.query);
      }
    },
    // reset() {
    //   this.query = "";
    // },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/_mixins.scss";

header {
  height: 100px;
  background-color: black;
  .container {
    height: 100%;
    @include flex("vertical");
    justify-content: space-between;
    figure {
      height: 100%;
      @include flex("vertical");
      img {
        height: 80%;
      }
      figcaption {
        color: red;
        font-size: 2rem;
        text-transform: uppercase;
        margin-left: 1rem;
      }
    }
    #search {
      * {
        padding: 10px;
      }
    }
  }
}
</style>
