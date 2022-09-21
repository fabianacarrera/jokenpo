<template>
  <div id="app">
    <MainCard title="Jo ken PÔ !"></MainCard>
  </div>
</template>

<script>
import MainCard from "./components/MainCard.vue";

export default {
  name: "App",
  components: {
    MainCard,
  },
};
</script>

<style>
@import url("https://rsms.me/inter/inter.css");

html {
  font-family: "Inter", sans-serif;
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  height: 100vh;
}
</style>
