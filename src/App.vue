<template>
  <div id="app">
    <MainCard
      :title="titleMessage"
      :painelMessage="painelMessage"
      :buttonLabel="buttonLabel"
    >
    </MainCard>
  </div>
</template>

<script>
import MainCard from "./components/MainCard.vue";

export default {
  name: "App",
  components: {
    MainCard,
  },
  data: function () {
    return {
      titleMessage: "Jo ken PÔ !",
      painelMessage: "Faça sua jogada!",
      buttonLabel: "recomeçar",
    };
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
