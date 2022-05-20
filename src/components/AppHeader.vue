<template>
  <header class="my_header d-flex align-items-center ps-4">
    <img src="../assets/img/logo-small.svg" alt="">
  </header>
</template>

<script>
export default {
  name: "AppHeader",
}
</script>

<style lang="scss" scoped>
@import "../style/variables.scss";

.my_header {
  height: $header-height;
  background-color: #2e3a46;

  img {
    height: 40px;
  }
}
</style>