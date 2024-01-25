<script setup lang="ts">
import router from "@/router";

const props = defineProps({
  username: String,
  password: String,
  role: String,
  loggedIn: Boolean
})
console.log(props.loggedIn)

if (!props.loggedIn){
  router.push('/login')
}
</script>

<template>
  <div>
    <h1>Member Page</h1>
      <!-- Your content here -->
    </div>
</template>

<style scoped>
</style>