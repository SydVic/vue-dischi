<template>
  <div>
    <label class="my_artist-input" for="artist">Scegli un artista</label>
    <select 
    name="artist" 
    id="artist" 
    @change="$emit('selectArtist', musicArtist)"  
    v-model="musicArtist"
    >
      <option value="all">All</option>
      <option value="bon jovi">Bon Jovi</option>
      <option value="queen">Queen</option>
      <option value="sting">Sting</option>
      <option value="steve godd band">SteveGodd Band</option>
      <option value="iron maiden">Iron Maiden</option>
      <option value="eric clapton">Eric Clapton</option>
      <option value="deep purple">Deep Purple</option>
      <option value="metallica">Metallica</option>
      <option value="dave weckl">Dave Weckkl</option>
      <option value="michael jacjson">Michael Jacjson</option>
    </select>
  </div>
</template>

<script>
export default {
  name: "AppArtistSearch",
  data: function() {
    return {
      musicArtist: "",
    }
  }
}
</script>

<style lang="scss" scoped>
  .my_artist-input {
    color: white;
  }
</style>