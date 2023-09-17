<template>
  <form @submit.prevent="handleSubmit">
    <label>Email:</label>
    <input type="email" required v-model="email" />

    <label>Password:</label>
    <input type="password" required v-model="password" />
    <div v-if="passwordError" class="error">{{ passwordError }}</div>

    <label>Role:</label>
    <select v-model="role">
      <option value="developer">Web Developer</option>
      <option value="designer">Web Designer</option>
    </select>

    <label>Skills:</label>
    <input type="text" v-model="tempSkill" @keyup.alt="addSkill" />
    <div v-for="skill in skills" :key="skill" class="pill" @click="removeSkill">
      {{ skill }}
    </div>

    <div class="terms">
      <input type="checkbox" required v-model="terms" />
      <label>Accept terms and conditions</label>
    </div>

    <div class="submit">
      <button>Create an Account</button>
    </div>
  </form>

  <p>Email: {{ email }}</p>
  <p>Password: {{ password }}</p>
  <p>Role: {{ role }}</p>
  <p>Terms accepted: {{ terms }}</p>
</template>

<script>
  export default {
    data() {
      return {
        email: '',
        password: '',
        role: 'designer',
        terms: false,
        tempSkill: '',
        skills: [],
        passwordError: '',
      }
    },
    methods: {
      addSkill(e) {
        if (e.key === ',' && this.tempSkill) {
          if (!this.skills.includes(this.tempSkill)) {
            this.skills.push(this.tempSkill)
          }
          this.tempSkill = ''
        }
      },
      removeSkill(e) {
        this.skills = this.skills.filter((skill) => skill !== e.target.textContent)
      },
      handleSubmit() {
        this.passwordError = this.password.length > 5 ? '' : 'Password must be at least 6 chars long'

        if (!this.passwordError) {
          console.log('email: ', this.email)
          console.log('password: ', this.password)
          console.log('role: ', this.role)
          console.log('skills: ', this.skills)
          console.log('terms.accepted: ', this.terms)
        }
      },
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
  .pill {
    display: inline-block;
    margin: 20px 10px 0 0;
    padding: 6px 12px;
    background: #eee;
    border-radius: 20px;
    font-size: 12px;
    letter-spacing: 1px;
    font-weight: 700;
    color: #777;
    cursor: pointer;
  }
  button {
    background: #0b6dff;
    padding: 10px 20px;
    margin-top: 20px;
    color: white;
    border-radius: 20px;
    cursor: pointer;
  }
  .submit {
    text-align: center;
  }
  .error {
    color: #ff0062;
    font-size: 0.8em;
    font-weight: 700;
  }
</style>
