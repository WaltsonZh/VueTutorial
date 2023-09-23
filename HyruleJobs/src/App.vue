<template>
  <div class="app">
    <p>{{ name }} - {{ age }}</p>
    <button @click="changeName('zelda')">change name</button>
    <button @click="changeAge('35')">change age</button>
  </div>
</template>

<!--options API-->
<!-- <script lang="ts">
  import { defineComponent } from 'vue'

  export default defineComponent({
    name: 'App',
    components: {},
    data() {
      return {
        name: 'Link',
        age: 25 as number | string,
      }
    },
    methods: {
      changeName(name: string) {
        this.name = name
        return name
      },
      changeAge(age: string | number) {
        this.age = age
        return age
      },
    },
  })
</script> -->

<!--composition API-->
<script setup lang="ts">
  import { ref } from 'vue'

  const name = ref('Link')
  const age = ref<number | string>(25)

  const changeName = (newName: string) => {
    name.value = newName
  }

  const changeAge = (newAge: number | string) => {
    age.value = newAge
  }
</script>

<style scoped></style>
