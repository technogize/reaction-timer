<template>
  <div>
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