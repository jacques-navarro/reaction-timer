<template>
  <h1>Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying">Play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame" />
  <Results v-if="showResults" :score="score"/>
</template>

<script>
import Block from "./components/Block.vue";
import Results from './components/Results.vue'

export default {
  name: "App",
  components: { Block, Results },

  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false,
    };
  },

  methods: {
    start() {
      this.delay = Math.floor(Math.random() * 5000) + 2000;
      this.isPlaying = true;
      this.showResults = false;
      console.log(`Delay: ${this.delay}`);
    },

    endGame(reactionTime) {
      this.score = reactionTime;
      this.isPlaying = false;
      this.showResults = true;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
</style>
