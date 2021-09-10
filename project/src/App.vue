<template>
  <div id="app">
    <Header />
    <main>
      <Library />
    </main>
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import Library from "@/components/Library.vue";

export default {
  name: "App",
  components: {
    Header,
    Library,
  },
};
</script>

<style lang="scss">
@import "assets/scss/_style.scss";
</style>
