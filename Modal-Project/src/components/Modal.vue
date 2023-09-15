<script>
  export default {
    props: ['theme'],
    methods: {
      closeModal() {
        this.$emit('close')
      },
    },
  }
</script>

<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <slot>default content</slot>
      <div class="actions">
        <slot name="links"></slot>
        <slot name="closeModal"></slot>
      </div>
    </div>
  </div>
</template>

<style scoped>
  .modal {
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: white;
    border-radius: 10px;
    display: grid;
    gap: 1em;
    place-items: center;
  }

  .backdrop {
    top: 0;
    position: fixed;
    background: rgba(0, 0, 0, 0.5);
    width: 100%;
    height: 100%;
  }

  .sale {
    background: crimson;
    color: white;
  }

  .actions {
    width: 100%;
    text-align: center;
    display: flex;
    justify-content: space-around;
  }
</style>
