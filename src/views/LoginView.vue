<script setup>
import { ref } from 'vue'

const username = ref('')
const password = ref('')

const login = async () => {
  console.log(`${username.value}  ${password.value}`)
  // Save the value
  // axios.post('');
}
</script>

<template>
  <div class="login-container">
    <div class="login-form">
      <h1>Login</h1>
      <form @submit.prevent="login">
        <div class="form-group">
          <input class="form-input" type="text" placeholder="Enter username" v-model="username" />
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
          <button class="form-button" type="submit">Login</button>
        </div>
      </form>
      <p>Don't have an account? <router-link to="/signup">Sign up</router-link></p>
    </div>
  </div>
</template>

<style scoped>
.login-container {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100vh;
}

.login-form {
  background-color: #f5f5f5;
  width: 70%;
  padding: 3%;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.login-form h1 {
  text-align: center;
  color: #333;
  font-family: 'Courier New', Courier, monospace;
}

.login-form .form-group {
  margin-bottom: 2%;
}

.login-form .form-input {
  width: 100%;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}

.login-form .form-button {
  background-color: #4caf50;
  color: white;
  padding: 10px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  width: 100%;
}

.login-form .form-button:hover {
  background-color: #45a049;
}
</style>
