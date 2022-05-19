<template>
  <section class="main-content d-flex justify-content-center align-items-center">
    <div v-if="loading">
      <AppLoading />
    </div>
    <div v-else class="my_container pt-5">
      <div class="row row-cols-5">
        <DiscCard v-for="(item, index) in discs" :key="index" :disc="item"/>
      </div>
    </div>
  </section>
</template>

<script>
import DiscCard from "./DiscCard.vue";
import AppLoading from "./AppLoading.vue";
import axios from "axios";

export default {
  name: "AppContent",
  components: {
    DiscCard,
    AppLoading,
  },
  data: function() {
    return {
      discs: [],
      loading: true
    }
  },
  created() {
    axios.get("https://flynn.boolean.careers/exercises/api/array/music")
    .then((resp) => {
      this.discs = resp.data.response;
      this.loading = false;
    });
  }
}
</script>

<style lang="scss" scoped>

.my_container {
  width: 70%;
  margin: 0 auto;
}
</style>