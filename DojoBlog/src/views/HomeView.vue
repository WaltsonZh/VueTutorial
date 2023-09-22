<template>
  <div class="home">
    <h1>Home</h1>
    <div v-if="error">{{ error }}</div>
    <div v-if="posts.length"><PostList :posts="posts" /></div>
    <div v-else>Loading...</div>
  </div>
</template>

<script setup>
  import PostList from '../components/PostList.vue'
  import getPosts from '../composables/getPosts'

  const { posts, error, load } = getPosts()
  
  load()
</script>

<style scoped>
  div {
    margin: 2em;
    display: grid;
    place-items: center;
    gap: 1em;
  }
</style>
