<template>
  <div class="game-over">
    <h2>GAME OVER!</h2>
    <div>You cannot click before you see the green block</div>
  </div>
</template>

<script>
export default {
  name: 'Failed'
}
</script>

<style>
  .game-over {
    color: #721c24;
    background-color: #f8d7da;
    border-color: #f5c6cb;
    position: relative;
    padding: .75rem 1.25rem;
    margin-bottom: 1rem;
    margin-top: 20px;
    border: 1px solid transparent;
    border-radius: .25rem;
  }

  .game-over h2 {
    margin-top: 0;
  }
</style>