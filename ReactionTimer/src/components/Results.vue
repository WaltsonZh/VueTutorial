<template>
  <p v-if="showResult">Reaction time: {{ score }} ms</p>
</template>

<script>
export default {
  props:['showResult', 'score']
}
</script>

<style scoped>
</style>