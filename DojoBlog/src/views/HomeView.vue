<template>
  <div class="home">
    <h1>Home</h1>
    <PostList :posts="posts" />
  </div>
</template>

<script setup>
  import { ref } from 'vue'
  import PostList from '../components/PostList.vue'

  const posts = ref([
    { title: 'welcome to the blog', body: 'Lorem ipsum', id: 1 },
    { title: 'top 5 CSS tips', body: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, magni hic! Quia, enim minima alias tempora eveniet, iure ad similique repellat ut adipisci aliquid debitis, voluptatum provident eius. Facere quisquam natus, repellat laborum quibusdam expedita provident vel dolor eum sapiente magnam, autem quaerat, quas quasi nihil pariatur earum! Autem, nulla molestiae? Dolorum sint quis et vero assumenda nostrum, porro ipsa quaerat ducimus saepe non reiciendis temporibus nemo consectetur earum blanditiis debitis ab rem aperiam esse fugit aliquid cumque? Perspiciatis veritatis ut quae aperiam placeat tempore quo doloremque exercitationem accusamus, asperiores ullam recusandae aspernatur ad enim fugit dignissimos ducimus! Nihil labore atque officia eaque, reiciendis beatae voluptatum, distinctio molestiae molestias, voluptatibus autem repudiandae vitae? Repellat, neque vero. Veniam aperiam animi facere, odio asperiores aliquid, nulla culpa accusamus quisquam nihil, inventore nostrum! Veritatis magni totam neque porro ex quas maxime cumque, qui, ad quia impedit aliquam, hic distinctio harum in. In eligendi qui, corporis dicta voluptatem suscipit? Quae explicabo, libero laborum debitis aliquam iure dolor hic deleniti nihil autem omnis ea dolore atque nam rerum veniam ullam sed doloribus? Amet totam blanditiis voluptas asperiores ab. Consequuntur nemo harum praesentium illum totam, enim dolor quasi similique eaque. Eaque dolor qui fugit. Consequuntur, corrupti!', id: 2 },
  ])
</script>

<style scoped>
  div {
    margin: 2em;
    display: grid;
    place-items: center;
    gap: 1em;
  }
</style>
