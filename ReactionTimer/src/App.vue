<script>
  import Block from './components/Block.vue'

  export default {
    name: 'App',
    components: { Block },
    data() {
      return {
        isPlaying: false,
        delay: null,
      }
    },
    methods: {
      start() {
        this.delay = 2000 + Math.random() * 5000
        this.isPlaying = true
      },
    },
  }
</script>

<template>
  <h1>Ninja Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying">play</button>
  <Block :delay="delay" v-if="isPlaying" />
</template>

<style scoped>
  h1 {
    margin: 2em;
  }
  button {
    width: 200px;
    height: 2em;
    border-radius: 10px;
    background: #81fadc;
    cursor: pointer;
  }
</style>
