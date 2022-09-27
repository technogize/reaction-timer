<template>
  <div v-if="showBlock" class="block">
    Click me {{delay}}
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
      showBlock: false
    }
  },
  mounted() {
    // Lifecycle hook
    console.log('Component has mounted');
    console.log('this.delay', this.delay);
    
    setTimeout(() => {
      this.showBlock = true;
      this.startTimer();
    }, this.delay);
  },
  methods: {
    startTimer() {
      
    },
    stopTimer() {

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
