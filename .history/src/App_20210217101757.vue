<template>
  <h1>Reaction Timer</h1>
  <p>Test your reactions. Click/tap the green box as soon as it appears.</p>
  <button class="start-button" @click="start" :disabled="isPlaying">Start</button>
  <Results v-if="showResults" :score="score" />
  <Block v-if="isPlaying" :delay="delay" @cheatedGame="gameEndedNoResults" @endGame="gameFinished" />
  <Failed v-if="failed" />
</template>

<script>
import Block from './components/Block.vue';
import Results from './components/Results.vue';
import Failed from './components/Failed.vue';

export default {
  name: 'App',
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false,
      failed: false
    }
  },
  components: {
    Block,
    Results,
    Failed
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      this.showResults = false;
      this.failed = false;
    },
    gameFinished(results) {
      this.score = results;
      this.showResults = true;
      this.isPlaying = false;
    },
    gameEndedNoResults() {
      this.isPlaying = false;
      this.failed = true;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  max-width: 1440px;
  margin: 0 auto;
}

.start-button {
  background: rgb(0, 185, 130);
  border: 0;
  border-radius: 3px;
  padding: 10px 15px;
  color: white;
  font-size: 18px;
}

.start-button:disabled {
  background: rgb(190, 190, 190);
  cursor: not-allowed;
}
</style>
