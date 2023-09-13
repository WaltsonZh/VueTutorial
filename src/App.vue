<script setup>
  import { computed, ref } from 'vue'

  const name = ref('Waltson')
  const count = ref(0)
  const showName = ref(true)
  const x = ref()
  const y = ref()
  const books = ref([
    { title: 'name of the wind', author: 'patrick rothfuss', isFav: true },
    { title: 'the way of kings', author: 'brandon sanderson', isFav: false },
    { title: 'the final empire', author: 'brandon sanderson', isFav: false },
  ])
  const url = ref('https://vuejs.org/')

  const toggleName = () => {
    if (name.value === 'Waltson') name.value = 'Vue'
    else name.value = 'Waltson'
  }

  const toggleShowName = () => {
    showName.value = !showName.value
  }

  const handleEvent = (e, data) => {
    console.log(e, e.type)
    if (data) {
      console.log(data)
    }
  }

  const handleMouseMove = (e) => {
    x.value = e.offsetX
    y.value = e.offsetY
  }

  const toggleFav = (book) => {
    book.isFav = !book.isFav
  }

  const filteredBooks = computed(() => {
    return books.value.filter((book) => book.isFav)
  })
</script>

<template>
  <h1 v-if="showName">Hello {{ name }}!</h1>

  <div class="counter">
    <button v-on:click="count++">+</button>
    <span>{{ count }}</span>
    <button v-on:click="count--">-</button>
  </div>

  <div @click="toggleName">Change name</div>

  <button class="toggle" @click="toggleShowName">
    <span v-if="showName">Hide Name</span>
    <span v-else>Show Name</span>
  </button>

  <div v-show="showName">currently showing name</div>

  <div class="box" @mouseover="handleEvent($event, 5)">mouseover (enter)</div>
  <div class="box" @mouseleave="handleEvent">mouseleave</div>
  <div class="box" @dblclick="handleEvent">double click</div>
  <div class="box" @mousemove="handleMouseMove">{{ x }} - {{ y }}</div>

  <ul>
    <li v-for="book in books" :class="{ fav: book.isFav }" @click="toggleFav(book)">
      {{ book.title }} - {{ book.author }}
    </li>
  </ul>

  <ul>
    <li v-for="book in filteredBooks">
      {{ book.title }} - {{ book.author }}
    </li>
  </ul>

  <a :href="url" target="_blank" >{{ url }}</a>
</template>

<style scoped>
  .counter {
    display: flex;
    gap: 1em;
  }
  .counter button {
    width: 2em;
  }
  .toggle {
    width: 30%;
  }
  .box {
    width: 400px;
    padding: 100px 0;
    text-align: center;
    background: #ddd;
    margin: 10px;
    text-align: center;
  }

  li {
    list-style-type: none;
  }
  .fav {
    color: red;
  }
</style>
