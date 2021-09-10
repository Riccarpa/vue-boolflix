<template>
  <section id="library">
    <div class="container">
      <Card />
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
};
</script>

<style lang="scss" scoped></style>
