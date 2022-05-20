<template>
  <!-- <section class="my_main-content d-flex justify-content-center align-items-center pb-5"> -->
  <section class="my_main-content pb-5">
    <div v-if="loading">
      <AppLoading />
    </div>
    <div v-else class="my_container">
      <AppMusicSearch @selectMusicGenre="musicGenre($event)"/>
      <AppArtistSearch @selectArtist="musicArtist($event)"/>
      <div class="row row-cols-5">
        <DiscCard v-for="(item, index) in filterDiscs" :key="index" :disc="item"/>
      </div>
    </div>
  </section>
</template>

<script>
import DiscCard from "./DiscCard.vue";
import AppLoading from "./AppLoading.vue";
import AppMusicSearch from "./AppMusicSearch.vue";
import AppArtistSearch from "./AppArtistSearch.vue";
import axios from "axios";

export default {
  name: "AppContent",
  components: {
    DiscCard,
    AppLoading,
    AppMusicSearch,
    AppArtistSearch,
  },
  data: function() {
    return {
      discs: [],
      genreSelected: "all",
      artistSelected: "all",
      loading: true
    }
  },
  methods: {
    musicGenre: function(optionSelected) {
      this.genreSelected = optionSelected;
    },
    musicArtist: function(optionSelected) {
      this.artistSelected = optionSelected;
    },
  },
  computed: {
    filterDiscs() {
      let filteredDiscArray = [];
      if (this.genreSelected === "all") {
        filteredDiscArray = this.discs;
      } else {
        filteredDiscArray = this.discs.filter((item) => {
          return item.genre.toLowerCase() === this.genreSelected;
        })
      }
      return filteredDiscArray;
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
@import "../style/variables.scss";

.my_main-content {
  height: calc(100vh - $header-height);

  .my_container {
    width: 70%;
    margin: 0 auto;
  }
}
</style>