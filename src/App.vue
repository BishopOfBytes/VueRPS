<template>
  <div id="top-bar" class="bar">
    <DisplayBox>2</DisplayBox>
    <DisplayBox>Current State</DisplayBox>
    <DisplayBox>0</DisplayBox>
  </div>
  <div id="bottom-bar" class="bar">
    <div class="player">
      <!-- Player 1 -->
      <ImageBox :source="rockImage"></ImageBox>
      <span>{{ p1name }}</span>
    </div>
    <div id="menu">
      <DisplayBox v-if="gameState === 1">Menu</DisplayBox>
      <InputBox v-if="gameState === 1" @text-change="p1name = $event" :defaultValue="p1name">Player 1 Name</InputBox>
      <InputBox v-if="gameState === 1" @text-change="p2name = $event" :defaultValue="p2name">Player 2 Name</InputBox>
      <InputBox v-if="gameState === 1" @text-change="setWinningScore($event)" :defaultValue="winningScore">Winning Score</InputBox>
      <GameButton v-if="gameState === 1" @click="gameState = 2">Play</GameButton>
      <DisplayBox v-if="gameState === 2">Player 1 Choose</DisplayBox>
      <MultiChoiceBox v-if="gameState === 2" :options="['Rock', 'Paper', 'Scissors']"></MultiChoiceBox>
    </div>
    <div class="player">
      <!-- Player 2 -->
      <ImageBox :source="scissorsImage"></ImageBox>
      <span>{{ p2name }}</span>
    </div>
  </div>
</template>

<script>
import DisplayBox from './components/DisplayBox.vue';
import ImageBox from './components/ImageBox.vue';
import InputBox from './components/InputBox.vue';
import GameButton from './components/GameButton.vue';
import MultiChoiceBox from './components/MultiChoiceBox.vue';

let GAME_STATES = {
  PREGAME: 1,
  ACTIVE: 2,
  POSTGAME: 3
};

export default {
  name: 'RPS',
  components: {
    DisplayBox,
    ImageBox,
    InputBox,
    GameButton,
    MultiChoiceBox
  },
  data: function() {
    return {
      rockImage: require('./assets/rock.jpg'),
      paperImage: require('./assets/paper.jpg'),
      scissorsImage: require('./assets/scissors.jpg'),
      p1name: 'Player 1',
      p2name: 'Player 2',
      winningScore: 10,
      gameState: GAME_STATES.PREGAME
    }
  },
  methods: {
    setWinningScore(val) {
      this.winningScore = parseInt(val);
    }
  }
}
</script>

<style>
.bar {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  justify-items: center;
  align-items: center;
}
#top-bar {
  background-color: rgba(255, 0, 0, 0.1);
  margin: 1.5rem;
  padding: 1rem;
}
#bottom-bar {
  background-color: rgba(0, 0, 255, 0.1);
  margin: 1.5rem;
  padding: 1rem;
}
.player {
  display: grid;
  justify-items: center;
}
</style>
