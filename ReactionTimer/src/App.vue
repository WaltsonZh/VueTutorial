<template>
  <h1>Ninja Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying">play</button>
  <Block :delay="delay" v-if="isPlaying" @end="endGame" />
  <Results :showResult="showResult" :score="score" />
</template>

<script>
  import Block from './components/Block.vue'
  import Results from './components/Results.vue'

  export default {
    name: 'App',
    components: { Block, Results },
    data() {
      return {
        isPlaying: false,
        delay: null,
        score: null,
        showResult: false,
      }
    },
    methods: {
      start() {
        this.delay = 2000 + Math.random() * 5000
        this.isPlaying = true
        this.showResult = false
      },
      endGame(reactionTime) {
        this.score = reactionTime
        this.isPlaying = false
        this.showResult = true
      },
    },
  }
</script>

<style scoped>
  h1 {
    margin-top: 2em;
  }
  button {
    width: 200px;
    height: 2em;
    border-radius: 10px;
    background: #81fadc;
    cursor: pointer;
  }
</style>
