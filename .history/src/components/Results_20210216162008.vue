<template>
  <div class="results">
    Reaction time: {{ score }}ms
  </div>
</template>

<script>
export default {
  name: 'Results',
  props: [
    'score'
  ]
}
</script>


<style scoped>
  .results {
    color: #004085;
    background-color: #cce5ff;
    border-color: #b8daff;
    position: relative;
    padding: .75rem 1.25rem;
    margin-bottom: 1rem;
    border: 1px solid transparent;
    border-radius: .25rem;

  }
</style>
