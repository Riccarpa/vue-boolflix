<template>
  <section id="library">
    <div class="container">
      <Card v-for="(moovie, index) in moovies" :moovie="moovie" :key="index" />
    </div>
  </section>
</template>

<script>
import Card from "@/components/Card.vue";

export default {
  name: "Library",
  components: {
    Card,
  },
  props: ["moovies"],
};
</script>

<style lang="scss" scoped></style>
