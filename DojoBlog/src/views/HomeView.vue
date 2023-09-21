<template>
  <div class="home">
    <h1>Home</h1>
    <input type="text" v-model="search" />
    <p>search term - {{ search }}</p>
    <div v-for="name in matchingNames" :key="name">{{ name }}</div>
    <button @click="handleClick">stop watching</button>
  </div>
</template>

<script setup>
  import { ref, computed, watch, watchEffect } from 'vue'

  const search = ref('')
  const names = ref(['mario', 'yoshi', 'luigi', 'toad', 'bowser', 'koopa', 'peach'])
  
  const stopWatch = watch(search, () => {
    console.log('watch function run')
  })

  const stopEffect = watchEffect(() => {
    console.log('watchEffect function ran')
  })

  const handleClick = () => {
    stopWatch()
    stopEffect()
  }

  const matchingNames = computed(() => {
    return names.value.filter((name) => name.includes(search.value))
  })
</script>

<style scoped>
  div {
    margin: 2em;
    display: grid;
    place-items: center;
    gap: 1em;
  }
</style>
