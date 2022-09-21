<template>
  <div class="card">
    <div class="card-header">
      <h2 class="card-title">{{ title }}</h2>
    </div>
    <div class="card-content">
      <div class="card-content-painel">
        <p>
          <font-awesome-icon
            class="gamepad"
            icon="fa-solid fa-gamepad"
            :mask="['fas', 'square-full']"
          />
        </p>
        <p>Faça sua jogada!</p>
      </div>
      <div class="card-content-options">
        <div class="card-options-icons">
          <div class="card-icon-border">
            <font-awesome-icon icon="fa-solid fa-hand-fist" />
          </div>
          <div class="card-icon-border">
            <font-awesome-icon icon="fa-solid fa-hand" />
          </div>
          <div><font-awesome-icon icon="fa-solid fa-hand-scissors" /></div>
        </div>
      </div>
    </div>
    <svg height="0" width="0">
      <linearGradient id="grad" x1="0%" y1="0%" x2="100%" y2="0%">
        <stop
          offset="0%"
          style="stop-color: rgb(150, 30, 244); stop-opacity: 1"
        />
        <stop
          offset="100%"
          style="stop-color: rgb(227, 88, 88); stop-opacity: 1"
        />
      </linearGradient>
    </svg>
  </div>
</template>

<script>
export default {
  name: "MainCard",
  props: {
    title: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.card {
  background-color: #fff;
  border-width: 2px;
  border-style: solid;
  border-image: linear-gradient(84.45deg, #961ef4 0%, #e35858 100%) 1;
  margin: auto auto;
  display: flex;
  flex-direction: column;
  width: 500px;
  height: 450px;
}

.card-header {
  position: relative;
  width: 511px;
  height: 90px;
  left: -5px;
  top: -5px;
  color: #fff;
  background: linear-gradient(84.45deg, #961ef4 0%, #e35858 100%);
  box-shadow: 0px 7px 5px -5px rgba(0, 0, 0, 0.25);
  border-radius: 10px;
}

.card-title {
  position: absolute;
  margin: 0;
  top: 50%;
  left: 50%;
  margin-right: -50%;
  transform: translate(-50%, -50%);
  font-size: 36px;
}

.card-content {
  margin: auto auto;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-evenly;
  height: 350px;
}

.card-content-painel {
  text-align: center;
  font-size: 20px;
}

.gamepad {
  font-size: 70px;
}

.fa-gamepad * {
  fill: url(#grad);
}

p {
  margin: 0;
  padding: 0;
  background: -webkit-linear-gradient(84.45deg, #961ef4 0%, #e35858 100%);
  background-clip: text;
  -webkit-text-fill-color: transparent;
  font-weight: bold;
  padding: 5px;
}

.card-content-button {
  width: 150px;
  padding: 8px 15px;
  border-radius: 15px;
  color: #fff;
  font-size: 15px;
  background-color: #00a78e;
  border: none;
  text-transform: uppercase;
  font-weight: bold;
}

.card-content-options {
  display: flex;
  width: 380px;
  height: 85px;
  color: #fff;
  background-color: #3a2a45;
  border-radius: 10px;
  align-items: center;
  justify-content: space-around;
}

.card-options-icons {
  width: 380px;
  font-size: 50px;
  cursor: pointer;
  text-align: center;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
}

.card-icon-border {
  border-right: 1px solid #fff;
}
</style>
