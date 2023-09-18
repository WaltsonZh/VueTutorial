<template>
  <nav>
    <RouterLink to="/">Home</RouterLink>
    <RouterLink to="/about">About</RouterLink>
    <RouterLink to="/jobs">Jobs</RouterLink>
  </nav>

  <RouterView />
</template>

<script>
  import { RouterLink, RouterView } from 'vue-router'
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
</style>
