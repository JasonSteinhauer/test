<script setup lang="ts">
import { ref } from 'vue'
import MemberView from "@/views/MemberView.vue";
import router from "@/router";

const usernameRef = ref('')
const passwordRef = ref('')
let loggedIn = ref('')
const role = ref('')

const users = [
  {username: "admin", password:"password1", role:"admin"},
  {username: "user", password:"password2", role:"member"},
  {username: "user2", password:"password3", role:"member"},
]
function handleLogin() {
  for (const u of users){
    if (u.username === usernameRef.value && u.password === passwordRef.value){
      loggedIn.value = "true"
      role.value = u.role
      console.log("test1")
      if (u.role === "member"){
        role.value = u.role
        router.push('/member')
        console.log("test2")
      }
    }
  }
}
</script>

<template>
  <div class="login-container">
    <h1>Login</h1>
    <form @submit.prevent="handleLogin">
      <input type="text" id="username" v-model="usernameRef" required placeholder="Username"/>
      <br>
      <input type="password" id="password" v-model="passwordRef" required placeholder="Password"/>
      <button type="submit" class="nlink">Login</button>
    </form>
  </div>
  <MemberView v-if="role === 'member'" :loggedIn="loggedIn"/>
</template>

<style scoped>
.login-container{
  width: fit-content;
  background-color: #333333;
  padding: 5rem;
  border-radius: 10%;
  border: 10px solid #8dbf67;
  justify-self: center;
  align-self: center;
  display: grid;
  justify-items: center;
  font-family: Roobert,-apple-system,BlinkMacSystemFont,"Segoe UI",Helvetica,Arial,sans-serif,"Apple Color Emoji","Segoe UI Emoji","Segoe UI Symbol";
  color: floralwhite;
  font-size: large;
}

.login-container form {
  display: grid;
  justify-items: center;
  align-content: center;
}

form input {
  font-family: inherit;
  width: 100%;
  border: 0;
  border-bottom: 2px solid gray;
  outline: 0;
  font-size: 1.3rem;
  color: white;
  padding: 7px 0;
  background: rgba(255,250,241,0.15);
  transition: border-color 0.2s;
}
&::placeholder {
  color: transparent;
}
</style>