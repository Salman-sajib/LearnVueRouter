<script setup>
import { useRoute, useRouter, RouterView } from "vue-router";
import cars from "../data/cars.json";
const route = useRoute();
const router = useRouter();
const carId = parseInt(route.params.id);
const car = cars.find((c) => c.id === carId);
</script>

<template>
  <main>
    <div v-if="car">
      <h1>{{ car.make }}</h1>
      <p>{{ car.body }}</p>
      <p>Year: {{ car.year }}</p>
      <p>Price: {{ car.price }}$</p>
      <button @click="router.push(`/cars/${carId}/contact`)">Contact</button>
    </div>
    <div v-else>
      <h1 class="errorMsg">Car not found</h1>
    </div>
    <RouterView />
  </main>
</template>

<style scoped>
main {
  width: 100%;
  display: flex;
  gap: 1rem;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin-block-start: 5rem;
}

div {
  width: min(100% - 2rem, 500px);
  color: rgb(0, 167, 47);
  padding-block: 5rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
  border: 5px solid rgb(0, 167, 47);
  border-radius: 1rem;
}

.errorMsg {
  color: red;
}

h1 {
  font-weight: bold;
  font-size: 2.5rem;
}

p {
  font-size: 1.1rem;
}

button {
  font-size: 1rem;
  padding: 0.5em 1.5em;
  margin-top: 1rem;
  background-color: rgb(0, 167, 47);
  border: none;
  border-radius: 0.3rem;
  color: rgb(37, 37, 37);
  transition: all 250ms ease-in-out;
}

button:hover,
button:focus {
  cursor: pointer;
  background-color: rgb(0, 143, 41);
  color: whitesmoke;
}
</style>
