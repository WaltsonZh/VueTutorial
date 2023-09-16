<template>
  <form>
    <label>Email</label>
    <input type="email" required>
  </form>
</template>

<script>
  export default {

  }
</script>

<style scoped>
  form {
    max-width: 800px;
    width: 70%;
    margin: 90px auto;
    background: white;
    text-align: left;
    padding: 40px;
    border-radius: 10px;
  }
  label {
    color: #aaa;
    background: transparent;
    display: inline-block;
    margin: 25px 0 15px;
    font-size: 0.6em;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: 700;
  }
  input {
    padding: 10px 6px;
    width: 100%;
    border-bottom: 1px solid #ddd;
    color: #555;
    background: transparent;
  }
</style>
