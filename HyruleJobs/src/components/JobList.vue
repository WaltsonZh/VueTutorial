<template>
  <div class="job-list">
    <p>Ordered by {{ order }}</p>
    <TransitionGroup name="list" tag="ul">
      <li v-for="job in orderedJobs" :key="job.id">
        <h2>{{ job.title }} - {{ job.location }}</h2>
        <div class="salary">
          <img src="../assets/rupee.svg" alt="rupee icon" />
          <p>{{ job.salary }} rupees</p>
        </div>
        <div class="description">Lorem ipsum dolor sit amet consectetur adipisicing elit. Deleniti, atque quibusdam doloribus voluptas, ut eum maiores eaque incidunt distinctio, repudiandae repellendus adipisci ea reprehenderit asperiores alias dolores minima voluptates sapiente!</div>
      </li>
    </TransitionGroup>
  </div>
</template>

<script setup lang="ts">
  import { computed } from 'vue'
  import Job from '../types/Jobs.ts'
  import OrderTerm from '../types/OrderTerm.ts'

  const props = defineProps<{
    jobs: Job[]
    order: OrderTerm
  }>()

  const orderedJobs = computed(() => {
    return [...props.jobs].sort((a: Job, b: Job) => {
      return a[props.order] > b[props.order] ? 1 : -1
    })
  })
</script>

<style scoped>
  .job-list {
    max-width: 960px;
    margin: 40px auto;
  }
  .job-list ul {
    padding: 1em;
    display: grid;
    gap: 16px;
  }
  .job-list li {
    list-style-type: none;
    background: white;
    padding: 16px;
    border-radius: 4px;
  }
  .job-list h2 {
    margin: 0 0 10px;
    text-transform: capitalize;
  }
  .salary {
    display: flex;
  }
  .salary img {
    width: 30px;
  }
  .salary p {
    color: #17bf66;
    font-weight: bold;
    margin: 10px 0;
  }
  .list-move {
    transition: all 1s;
  }
</style>
