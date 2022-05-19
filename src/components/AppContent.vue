<template>
  <section class="main-content">
    <div class="my_container pt-5">
      <div class="row row-cols-5">
        <DiscCard v-for="(item, index) in discs" :key="index" :disc="item"/>
      </div>
    </div>
  </section>
</template>

<script>
import DiscCard from "./DiscCard.vue";
import axios from "axios";

export default {
  name: "AppContent",
  components: {
    DiscCard,
  },
  data: function() {
    return {
      discs: []
    }
  },
  created() {
    axios.get("https://flynn.boolean.careers/exercises/api/array/music")
    .then((resp) => {
      this.discs = resp.data.response;
      console.log(resp.data.response);
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