<template>
  <div id="app">
    <AppHeader />
  </div>
</template>

<script>
import AppHeader from "./components/AppHeader";

export default {
  name: 'App',
  components: {
    AppHeader,
  }
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss"; 

body {
  background-color: #1e2d3b;
}
</style>
