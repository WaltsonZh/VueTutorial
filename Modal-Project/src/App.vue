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
        showModalTwo: false,
      }
    },
    methods: {
      toggleModal() {
        this.showModal = !this.showModal
      },
      toggleModalTwo() {
        this.showModalTwo = !this.showModalTwo
      },
    },
  }
</script>

<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>

  <Teleport to=".modals" v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
      <h1>Ninja Giveaway</h1>
      <p>Grab your ninja swag for half price!</p>
    </Modal>
  </Teleport>

  <Teleport to=".modals" v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <template v-slot:closeModal>
        <button @click="toggleModalTwo">close modal</button>
      </template>
    </Modal>
  </Teleport>

  <button @click.alt="toggleModal">open modal (alt)</button>
  <button @click.shift="toggleModalTwo">open modal 2 (shift)</button>
</template>

<style scoped>
  h1 {
    border-bottom: 1px solid #ddd;
    display: inline-block;
    padding-bottom: 10px;
  }
</style>
