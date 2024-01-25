<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div class="header">
    <nav>
      <RouterLink to="/" class="nlink" v-if="$route.path !== '/'">Home</RouterLink>
      <RouterLink to="/about" class="nlink" v-if="$route.path !== '/about'">About</RouterLink>
      <RouterLink to="/login" class="nlink" v-if="$route.path !== '/login'">Login</RouterLink>
    </nav>
  </div>
  <div class="container">
    <RouterView />
  </div>
</template>

<style>
.header {
  display: grid;
  width: 100%;
  height: 10vh;
  justify-content: end;
  align-content: center;
  background: rgb(0,0,0);
  background: linear-gradient(20deg, rgba(0,0,0,0) 54%, rgba(0,0,0,0.28617384453781514) 67%, rgba(2,0,36,0.6307116596638656) 100%);
}

.nlink {
  text-decoration: none;
  appearance: none;
  background-color: #8dbf67;
  border: 2px solid #1A1A1A;
  border-radius: 15px;
  box-sizing: border-box;
  color: #FFFFFF;
  cursor: pointer;
  display: inline-block;
  font-family: Roobert,-apple-system,BlinkMacSystemFont,"Segoe UI",Helvetica,Arial,sans-serif,"Apple Color Emoji","Segoe UI Emoji","Segoe UI Symbol";
  font-size: 16px;
  font-weight: 600;
  line-height: normal;
  margin: 1em;
  min-height: 60px;
  min-width: 0;
  outline: none;
  padding: 16px 24px;
  text-align: center;
  transition: all 300ms cubic-bezier(.23, 1, 0.32, 1);
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
  will-change: transform;
}

.nlink:hover {
  box-shadow: rgba(0, 0, 0, 0.25) 0 8px 15px;
  transform: translateY(-2px);
}

.nlink:active {
  box-shadow: none;
  transform: translateY(0);
}

.container {
  display: grid;
  height: 80%;
}
</style>