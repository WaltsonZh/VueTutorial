<template>
  <nav>
    <RouterLink to="/">Home</RouterLink>
    <RouterLink :to="{ name: 'About' }">About</RouterLink>
    <RouterLink :to="{ name: 'Jobs' }">Jobs</RouterLink>
  </nav>

  <div>
    <button @click="redirect">Redirect</button>
    <button @click="back">Go back</button>
    <button @click="forward">Go Forward</button>
  </div>

  <RouterView />
</template>

<script>
  import { RouterLink, RouterView } from 'vue-router'

  export default {
    methods: {
      redirect() {
        this.$router.push({ name: 'Home'})
      },
      back() {
        this.$router.go(-1)
      },
      forward() {
        this.$router.go(1)
      },
    },
  }
</script>

<style scoped>
  nav {
    padding: 1em;
    display: flex;
    gap: 1em;
  }
  nav a {
    font-size: 1.2em;
    text-decoration: none;
    color: black;
    font-weight: 700;
    padding: 0.5em;
    border-radius: 10px;
  }
  nav a.router-link-active {
    background: crimson;
    color: white;
  }
  button {
    margin: 0 10px;
    padding: 10px;
    border-radius: 4px;
    cursor: pointer;
  }
</style>
