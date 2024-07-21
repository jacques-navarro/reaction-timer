<template>
  <h1>Reaction Timer</h1>
  <button @click="start">Play</button>
</template>

<script>
export default {
  name: "App",
  components: {},

  data() {
    return {
      isPlaying: false,
      delay: null,
    };
  },

  methods: {
    start() {
      this.delay = Math.floor(Math.random() * 5000) + 2000
      this.isPlaying = true
      console.log(`Delay: ${this.delay}`)
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
