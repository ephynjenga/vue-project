<script setup>
import { ref } from 'vue'
import axios from 'axios'

const username = ref('john')
const email = ref('john@gmail.com')
const password = ref('john123')

const signup = async () => {
  console.log(`${username.value} ${email.value} ${password.value}`)
  // Save the value
  axios.post('http://127.0.0.1:8000', {
    username: username.value,
    email: email.value,
    password: password.value
  })
  // copy and paste the url fom your postman and you should be able to get your values  eg: {username, email, password}
}
</script>

<template>
  <div class="signup-container">
    <div class="signup-form">
      <h1>Register</h1>
      <form @submit.prevent="signup">
        <div class="form-group">
          <input class="form-input" type="text" placeholder="Enter username" v-model="username" />
        </div>
        <div class="form-group">
          <input class="form-input" type="email" placeholder="Enter email" v-model="email" />
        </div>
        <div class="form-group">
          <input
            class="form-input"
            type="password"
            placeholder="Enter password"
            v-model="password"
          />
        </div>
        <div class="form-group">
          <button class="form-button" type="submit">Signup</button>
        </div>
      </form>
      <p>{{ username }}</p>
    </div>
  </div>
</template>

<style scoped>
.signup-container {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100vh;
}

.signup-form {
  background-color: #f5f5f5;
  width: 70%;
  padding: 3%;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.signup-form h1 {
  text-align: center;
  color: #333;
  font-family: 'Courier New', Courier, monospace;
}

.signup-form .form-group {
  margin-bottom: 2%;
}

.signup-form .form-input {
  width: 100%;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}

.signup-form .form-button {
  background-color: #4caf50;
  color: white;
  padding: 10px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  width: 100%;
}

.signup-form .form-button:hover {
  background-color: #45a049;
}
</style>
