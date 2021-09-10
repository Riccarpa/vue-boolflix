<template>
  <header>
    <div class="container">
      <img src="@/assets/logo.png" alt="logo" />
      <div id="search">
        <input type="text" placeholder="Cerca..." />
        <button>Vai</button>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
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
  }
  #search {
    * {
      padding: 10px;
    }
  }
}
</style>
