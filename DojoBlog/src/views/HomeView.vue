<template>
  <div>
    Home
    <p>My name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">click me</button>
  </div>
</template>

<script>
  export default {
    setup() {
      let name = 'mario'
      let age = 30

      const handleClick = () => {
        console.log('clicked')
      }

      return { name, age, handleClick }
    },
  }
</script>
