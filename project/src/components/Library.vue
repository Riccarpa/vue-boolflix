<template>
  <section id="library">
    <div class="container">
      <h1 v-if="moovies.length > 0">Film</h1>
      <div class="movie-cards">
        <Card v-for="moovie in moovies" :moovie="moovie" :key="moovie.id" />
      </div>
      <h1 v-if="series.length > 0">Serie</h1>
      <div class="series-cards">
        <SeriesCard v-for="serie in series" :serie="serie" :key="serie.id" />
      </div>
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

<style lang="scss" scoped>
h1 {
  font-size: 40px;
  margin: 2rem;
}
.movie-cards {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}
.series-cards {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}
</style>
