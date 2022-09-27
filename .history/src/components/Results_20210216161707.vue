<template>
  Hi! {{ score }}ms
</template>

<script>
export default {
  name: 'Results',
  props: [
    'score'
  ]
}
</script>