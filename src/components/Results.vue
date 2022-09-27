<template>
  <div class="results">
    Reaction time: {{ score }}ms
    <h2 class="large">
      {{ rank }}
    </h2>
    <img class="rank-image" :src="imageSrc" />

    <p v-if="score >= 20">Keep trying! There are faster ranks than <strong>{{ rank }}</strong></p>
    <p v-if="score < 20">Congratulations, you have obtained the fastest rank of <strong>{{ rank }}</strong></p>
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
    if (this.score < 20) {
      this.rank = 'Warp speed!';
      this.imageSrc = 'https://media.giphy.com/media/jYh9UDh2OE7XW/giphy.gif';
    } else if (this.score < 250) {
      this.rank = 'Lightning!';
      this.imageSrc = 'https://media.giphy.com/media/VIEsDrchn6SQ62MoVc/giphy.gif';
    } else if (this.score < 400) {
      this.rank = 'Rapid reflexes!';
      this.imageSrc = 'https://media.giphy.com/media/B1uajA01vvL91Urtsp/giphy.gif';
    } else if (this.score < 600) {
      this.rank = 'Quite quick.';
      this.imageSrc = 'https://media.giphy.com/media/jS2Wv3E0xSiquMLPcA/giphy.gif';
    } else {
      this.rank = 'Slow... :/';
      this.imageSrc = 'https://media.giphy.com/media/3o6MbnqLhX5tJ5wNQQ/giphy.gif';
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

  .large {
    text-decoration: underline;
  }

  .rank-image {
    max-width: 100%;
  }
</style>
