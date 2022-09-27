<template>
  <div v-if="showBlock" class="block" @click="stopTimer">
    Click me
  </div>
</template>

<script>
export default {
  name: 'Block',
  props: [
    'delay'
  ],
  data() {
    return {
      showBlock: false,
      timer: null,
      reactionTime: 0
    }
  },
  mounted() {
    // Lifecycle hook
    setTimeout(() => {
      this.showBlock = true;
      this.startTimer();
    }, this.delay);
  },
  methods: {
    startTimer() {
      this.timer = setInterval(() => {
        this.reactionTime += 10;
      }, 10);
    },
    stopTimer() {
      clearInterval(this.timer);
      this.$emit('endGame', this.reactionTime);
    }
  }
}
</script>

<style scoped>
  .block {
    background: rgb(0, 185, 130);
    color: white;
    font-weight: bold;
    border-radius: 5px;
    text-align: center;
    max-width: 400px;
    padding: 30px;
    margin: 40px auto; 
  }
</style>
