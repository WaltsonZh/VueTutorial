<script>
  import Modal from './components/Modal.vue'

  export default {
    name: 'App',
    components: { Modal },
    data() {
      return {
        title: 'My First Vue App :)',
        header: 'Sign up for the Giveaway',
        text: 'Grab your ninja swag for half price!',
        showModal: false,
      }
    },
    methods: {
      toggleModal() {
        this.showModal = !this.showModal
      }
    }
  }
</script>

<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <div v-if="showModal">
    <Modal :header="header" :text="text" theme="sale" @close="toggleModal" />
  </div>
  <button @click.alt="toggleModal">open modal (alt)</button>
</template>

<style scoped>
  h1 {
    border-bottom: 1px solid #ddd;
    display: inline-block;
    padding-bottom: 10px;
  }
</style>
