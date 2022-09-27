<template>
  <div class="results">
    Reaction time: {{ score }}ms
    <h3 class="large">
      {{ rank }}
    </h3>
    <img :src="imageSrc" />
  </div>
</template>

<script>
export default {
  name: 'Results',
  props: [
    'score'
  ],
  data() {
    return {
      rank: null,
      imageSrc: null
    }
  },
  mounted() {
    if(this.score < 250) {
      this.rank = 'Lightning!';
      this.imageSrc = 'https://media.giphy.com/media/B1uajA01vvL91Urtsp/giphy.gif';
    } else if (this.score < 400) {
      this.rank = 'Rapid reflexes!';
    } else if (this.score < 600) {
      this.rank = 'Quite quick.';
    } else {
      this.rank = 'Slow... :/';
    }
  }
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
    margin: 15px 0;
  }
</style>
