<script setup>
import { ref } from 'vue'
// this is for count app project
const count = ref(0)
console.log(count.value)
//function increment(){
count.value++
</script>

<template>
  <!-- this is a navbar sectio -->
  <div class="nav">
    <router-link class="nav-item" to="/">Home</router-link>
    <router-link class="nav-item" to="/About">About</router-link>
    <router-link class="nav-item" to="/Services">Services</router-link>
    <router-link class="nav-item" to="/login">Login</router-link>
    <router-link class="nav-item" to="/SignUp">SignUp</router-link>
  </div>
  <router-view></router-view>
  <!-- this is the counter app -->
  <!--<h1> Couter App</h1>
    <h1>{{count}}</h1>
    <button @click=increment>Increment</button>
   <p>{{ count }}</p>-->
</template>

<style scoped>
.nav {
  background-color: green;
  padding: 14px 28px;
  align-items: center;
  justify-content: center;
}
.nav .nav-item {
  text-decoration: none;
  color: white;
  font-weight: bold;
  font-family: Courier, monospace;
  padding: 0px 28px;
  margin-right: 5px;
}
</style>
