<template>
  <form>
    <label>Email:</label>
    <input type="email" required v-model="email" />

    <label>Password:</label>
    <input type="password" required v-model="password" />

    <label>Role:</label>
    <select v-model="role">
      <option value="developer">Web Developer</option>
      <option value="designer">Web Designer</option>
    </select>

    <div class="terms">
      <input type="checkbox" required v-model="terms" />
      <label>Accept terms and conditions</label>
    </div>

    <div>
      <input type="checkbox" value="shaun" v-model="names" />
      <label>Shaun</label>
    </div>
    <div>
      <input type="checkbox" value="yoshi" v-model="names" />
      <label>Yoshi</label>
    </div>
    <div>
      <input type="checkbox" value="mario" v-model="names" />
      <label>Mario</label>
    </div>
  </form>

  <p>Email: {{ email }}</p>
  <p>Password: {{ password }}</p>
  <p>Role: {{ role }}</p>
  <p>Terms accepted: {{ terms }}</p>
  <p>Names: {{ names }}</p>
</template>

<script>
  export default {
    data() {
      return {
        email: 'mario',
        password: '',
        role: 'designer',
        terms: false,
        names: [],
      }
    },
  }
</script>

<style scoped>
  form {
    max-width: 800px;
    width: 70%;
    margin: 90px auto 0;
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
  input,
  select {
    padding: 10px 6px;
    width: 100%;
    border-bottom: 1px solid #ddd;
    color: #555;
    background: transparent;
  }
  div {
    background: transparent;
  }
  input[type='checkbox'] {
    display: inline-block;
    width: 16px;
    margin: 0 10px 0 0;
    position: relative;
    top: 2px;
  }
</style>
