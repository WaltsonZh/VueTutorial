<template>
  <div class="home">
    <h1>Home</h1>
    <h2>Refs</h2>
    <p>{{ ninjaOne.name }} - {{ ninjaOne.age }}</p>
    <button @click="updateNinjaOne">Update ninja one</button>
    <h2>Reactive</h2>
    <p>{{ ninjaTwo.name }} - {{ ninjaTwo.age }}</p>
    <button @click="updateNinjaTwo">Update ninja two</button>
  </div>
</template>

<script setup>
  import { ref, reactive } from 'vue'

  const ninjaOne = ref({ name: 'mario', age: 30})
  const ninjaTwo = reactive({ name: 'luigi', age: 35 })

  const updateNinjaOne = () => {
    ninjaOne.value.age = 40
  }

  const updateNinjaTwo = () => {
    ninjaTwo.age = 45
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
