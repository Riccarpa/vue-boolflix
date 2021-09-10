<template>
  <section id="library">
    <div class="container">
      <h1>Film</h1>
      <Card v-for="(moovie, index) in moovies" :moovie="moovie" :key="index" />
      <h1>Serie</h1>
      <SeriesCard
        v-for="(serie, index) in series"
        :serie="serie"
        :key="index"
      />
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
