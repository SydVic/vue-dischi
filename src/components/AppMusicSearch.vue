<template>
  <div>
    <label class="my_music-input" for="music-genres">Scegli un genere musicale</label>
    <select 
    name="music-genres" 
    id="music-genres" 
    @change="$emit('selectMusicGenre', musicGenre)"  
    v-model="musicGenre"
    >
      <option value="all">All</option>
      <option value="rock">Rock</option>
      <option value="pop">Pop</option>
      <option value="jazz">Jazz</option>
      <option value="metal">Metal</option>
    </select>
  </div>
</template>

<script>
export default {
  name: "AppMusicSearch",
  data: function() {
    return {
      musicGenre: "",
    }
  }
}
</script>

<style lang="scss" scoped>
  .my_music-input {
    color: white;
  }
</style>