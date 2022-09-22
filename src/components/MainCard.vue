<template>
  <div :class="classCard">
    <div :class="classHeader">
      <h2 class="card-title">{{ title }}</h2>
    </div>
    <div class="card-content">
      <template v-if="template">
        <div class="card-content-painel">
          <p>
            <font-awesome-icon
              class="gamepad"
              icon="fa-solid fa-gamepad"
              :mask="['fas', 'square-full']"
            />
          </p>
          <p>{{ painelMessage }}</p>
        </div>
      </template>
      <template v-else>
        <div class="card-content-painel">
          <label>
            {{ player }}
          </label>
          <label> VS </label>
          <label>
            {{ computer }}
          </label>
        </div>
      </template>
      <button
        v-if="clickedButton"
        type="button"
        class="card-content-button"
        @click="restart"
      >
        {{ buttonLabel }}
      </button>
      <div class="card-content-options">
        <div class="card-options-icons">
          <div class="icon-border clickEffect" @click="clickButton('rock')">
            <font-awesome-icon icon="fa-solid fa-hand-fist" />
          </div>
          <div class="icon-border clickEffect" @click="clickButton('paper')">
            <font-awesome-icon icon="fa-solid fa-hand" />
          </div>
          <div class="clickEffect" @click="clickButton('scissors')">
            <font-awesome-icon icon="fa-solid fa-hand-scissors" />
          </div>
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
    painelMessage: String,
    buttonLabel: String,
  },
  data: function () {
    return {
      results: {
        rock: {
          rock: 2,
          paper: 0,
          scissors: 1,
        },
        paper: {
          rock: 1,
          paper: 2,
          scissors: 0,
        },
        scissors: {
          rock: 0,
          paper: 1,
          scissors: 2,
        },
      },
      options: ["rock", "paper", "scissors"],
      clickedButton: false,
      player: "",
      computer: "",
      final: "",
      classCard: "card default-border",
      classHeader: "card-header default-background",
      playerIcon: "",
      computerIcon: "",
      template: true,
    };
  },
  methods: {
    clickButton: function (player) {
      this.clickedButton = true;

      let random = Math.floor(Math.random() * 3);
      this.computer = this.options[random];
      this.player = player;
      this.final = this.results[this.player][this.computer];

      console.log(this.random, this.final, this.player, this.final);

      switch (this.final) {
        case 0:
          this.classCard = "card lose-border";
          this.classHeader = "card-header lose-background";
          this.titleMessage = "Você Perdeu!";
          break;
        case 1:
          this.classCard = "card win-border";
          this.classHeader = "card-header win-background";
          this.titleMessage = "Você Venceu!";
          break;
        case 2:
          this.classCard = "card tie-border";
          this.classHeader = "card-header tie-background";
          this.titleMessage = "Empate";
      }

      this.template = false;
    },
    restart: function () {
      this.template = true;
      this.clickedButton = false;
      this.classCard = "card default-border";
      this.classHeader = "card-header default-background";
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.default-border {
  border-width: 2px;
  border-style: solid;
  border-image: linear-gradient(84.45deg, #961ef4 0%, #e35858 100%) 1;
}

.default-background {
  background: linear-gradient(84.45deg, #961ef4 0%, #e35858 100%);
}

.win-border {
  border: 2px solid #00a78e;
}

.lose-border {
  border: 2px solid #e35858;
}

.tie-border {
  border: 2px solid #3a2a45;
}

.win-background {
  background-color: #00a78e;
}

.lose-background {
  background-color: #e35858;
}

.tie-background {
  background-color: #3a2a45;
}

.card {
  background-color: #fff;
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
  cursor: pointer;
  box-shadow: 0 2px #999;
}

.card-content-button:hover {
  background-color: #018874;
}

.card-content-button:active {
  background-color: #056355;
  box-shadow: 0 4px #666;
  transform: translateY(4px);
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

.icon-border {
  border-right: 1px solid #fff;
}

.clickEffect:hover {
  color: rgb(212, 212, 212);
}

.clickEffect:active {
  color: rgb(126, 126, 126);
}
</style>
