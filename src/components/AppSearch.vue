<template>
  <div>
    <select 
    name="music-genres" 
    id="music-genres" 
    @change="$emit('selectMusicGenre', musicGenre)"  
    v-model="musicGenre"
    >
      <option value="all" selected>All</option>
      <option value="rock">Rock</option>
      <option value="pop">Pop</option>
      <option value="jazz">Jazz</option>
      <option value="metal">Metal</option>
    </select>
  </div>
</template>

<script>
export default {
  name: "appSearch",
  data: function() {
    return {
      musicGenre: "",
    }
  }
}
</script>

<style>

</style>