<template>
  <div id="app">
    <AppHeader />
    <AppContent />
  </div>
</template>

<script>
import AppHeader from "./components/AppHeader";
import AppContent from "./components/AppContent";

export default {
  name: "App",
  components: {
    AppHeader,
    AppContent,
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";

body {
  background-color: #1e2d3b;
}
</style>
