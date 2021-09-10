<template>
  <section id="library">
    <div class="container">
      <h1 v-if="moovies.length > 0">Film</h1>
      <Card v-for="moovie in moovies" :moovie="moovie" :key="moovie.id" />
      <h1 v-if="series.length > 0">Serie</h1>
      <SeriesCard v-for="serie in series" :serie="serie" :key="serie.id" />
    </div>
  </section>
</template>

<script>
import Card from "@/components/Card.vue";
import SeriesCard from "@/components/SeriesCard.vue";

export default {
  name: "Library",
  components: {
    Card,
    SeriesCard,
  },
  props: ["moovies", "series"],
};
</script>

<style lang="scss" scoped></style>
