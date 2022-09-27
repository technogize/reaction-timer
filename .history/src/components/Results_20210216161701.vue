<template>
  Hi! {{ score }}
</template>

<script>
export default {
  name: 'Results',
  props: [
    'score'
  ]
}
</script>