<template>
  <div id="app">
    <MainCard
      :title="title"
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
      title: "Jo ken PÔ !",
      painelMessage: "Faça sua jogada!",
      buttonLabel: "recomeçar",
    };
  },
};
</script>

<style>
@import url("https://rsms.me/inter/inter.css");
@import url("https://fonts.googleapis.com/css2?family=Knewave&display=swap");

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
