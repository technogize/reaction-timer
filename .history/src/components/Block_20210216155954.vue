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
    console.log('Component has mounted');
    console.log('this.delay', this.delay)
    setTimeout(function() {
      this.showBlock = true;
    }, this.delay);
  },
  updated() {
    console.log('Component has updated');
  }
  // methods: {
  //   closeModal() {
  //     //Custom event to close modal so that the parent app can update
  //     //Emit custom event named closeModal.
  //     this.$emit('closeModal');
  //   }
  // }
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
