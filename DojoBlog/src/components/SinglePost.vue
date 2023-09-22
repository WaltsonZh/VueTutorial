<template>
  <div>
    <RouterLink :to="{ name: 'Details', params: { id: post.id } }">
      <h3>{{ post.title }}</h3>
    </RouterLink>
    <p>{{ snippet }}</p>
    <span v-for="tag in post.tags" :key="tag"> #{{ tag }}</span>
  </div>
</template>

<script setup>
  import { computed } from 'vue'
  const props = defineProps(['post'])

  const snippet = computed(() => {
    return props.post.body.substring(0, 100) + '...'
  })
</script>

<style scoped></style>
