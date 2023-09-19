<template>
  <div>
    Home
    <p ref="p">My name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">click me</button>
    <button @click="age++">add 1 to age</button>
    <input type="text" v-model="name">
  </div>
</template>

<script>
import { ref } from 'vue'

  export default {
    setup() {
      const name = ref('mario')
      const age = ref(30)

      const p = ref('hello')
      console.log(p, p.value)

      const handleClick = () => {
        name.value = 'luigi'
        age.value = 35
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
