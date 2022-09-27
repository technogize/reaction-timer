<template>
  <h1>Ninja Reaction Timer</h1>
  <button class="start-button" @click="start" :disabled="isPlaying">Play</button>
  <Results v-if="showResults" :score="score" />
  <Block v-if="isPlaying" :delay="delay" @endGame="gameFinished" />
</template>

<script>
import Block from './components/Block.vue';
import Results from './components/Results.vue';

export default {
  name: 'App',
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false
    }
  },
  components: {
    Block,
    Results
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      this.showResults = false;
      console.log(this.delay);
    },
    gameFinished(results) {
      console.log('Results:', results);
      this.score = results;
      this.showResults = true;
      this.isPlaying = false;
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
}

.start-button {
  background: rgb(0, 185, 130);
  border: 0;
  border-radius: 3px;
  padding: 10px 15px
}
</style>
