<script setup lang="ts">
import router from "@/router";

const props = defineProps({
  loggedIn: String
})
const test = props.loggedIn
if (test === "true"){
  let out = false
  console.log("loggedin")
}

console.log(test)
debugger;

</script>

<template>
  <div>
    <h1>Mitglieder</h1>

  </div>
</template>

<style scoped>
</style>