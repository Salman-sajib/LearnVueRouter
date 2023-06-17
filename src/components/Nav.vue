<script setup>
import { RouterLink } from "vue-router";
</script>

<template>
  <div>
    <RouterLink active-class="active" to="/">Home</RouterLink>
    <RouterLink active-class="active" to="/about">About</RouterLink>
  </div>
</template>

<style scoped>
div {
  display: flex;
  gap: 1rem;
  align-items: center;
  justify-content: center;
}

a {
  font-size: 1.3rem;
  font-weight: bold;
  color: rgb(0, 167, 47);
  text-decoration: none;
  background-color: transparent;
  border: 1px solid rgb(0, 167, 47);
  border-radius: 0.4em;
  padding: 0.5em 1.5em;
}

.active {
  font-weight: bold;
  color: aliceblue;
  background-color: rgb(0, 167, 47);
}
</style>
