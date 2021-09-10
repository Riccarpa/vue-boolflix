<template>
  <div class="card">
    <ul>
      <li>TITOLO: {{ moovie.title }}</li>
      <li>TITOLO ORIGINALE: {{ moovie.original_title }}</li>
      <li>LINGUA: {{ moovie.original_language }}</li>
      <li>VOTO: {{ moovie.vote_average }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: ["moovie"],
};
</script>

<style lang="scss" scoped>
.card {
  margin: 2rem;
}
</style>
