<template>
  <div>
    Home
    <p ref="p">My name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">click me</button>
  </div>
</template>

<script>
import { ref } from 'vue'

  export default {
    setup() {
      let name = 'mario'
      let age = 30

      const p = ref('hello')
      console.log(p, p.value)

      const handleClick = () => {
        console.log(p, p.value)
        p.value.classList.add('test')
        p.value.textContent = 'hello, ninjas'
      }

      return { name, age, handleClick, p }
    },
  }
</script>

<style scoped>
  div {
    margin: 2em;
    display: grid;
    place-items: center;
    gap: 1em;
  }
</style>
