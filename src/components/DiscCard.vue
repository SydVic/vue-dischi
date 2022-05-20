<template>
  <div class="my_disc-card text-center mt-4 pt-3">
    <div class="my_card-wrapper h-100 px-3 pt-3">
      <div class="my_disc-img-wrapper">
        <img :src="disc.poster" :alt="disc.title + ' ' + disc.author">
      </div>
      <h4 class="my_disc-title text-uppercase mt-3">{{disc.title}}</h4>
      <div class="my_disc-author pt-3">{{disc.author}}</div>
      <div class="my_disc-year pb-2">{{disc.year}}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "DiscCard",
  props: {
    disc: Object
  }
}
</script>

<style lang="scss" scoped>
.my_card-wrapper {
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