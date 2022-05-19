<template>
  <div class="my_disc-card text-center">
    <div class="my_disc-img-wrapper">
      <img src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
    </div>
    <h4 class="my_disc-title text-uppercase">New Jersey</h4>
    <div class="my_disc-author pt-3">Bon Jovi</div>
    <div class="my_disc-year pb-5">1988</div>
  </div>
</template>

<script>
export default {
  name: "DiscCard",
}
</script>

<style lang="scss" scoped>
.my_disc-card {
  background-color: #2e3a46;

  h4 {
    color: white;
  }

  div {
    color: #707e7c;
  }

  img {
    max-width: 100%;
  }
}
</style>