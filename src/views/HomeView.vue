<script setup>
import cars from "../data/cars.json";
import { RouterLink } from "vue-router";
</script>

<template>
  <div>
    <h1>Home View</h1>
    <div class="cars">
      <RouterLink
        :to="`/cars/${car.id}`"
        v-for="car in cars"
        :key="car.id"
        href=""
      >
        {{ car.make }}
      </RouterLink>
    </div>
  </div>
</template>

<style scoped>
h1 {
  margin-block-end: 3rem;
  color: aliceblue;
  font-weight: bold;
  text-align: center;
}
.cars {
  width: min(100% - 1.5rem, 1200px);
  margin-inline: auto;
  display: flex;
  /* flex-direction: column; */
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
  gap: 2rem;
}

.cars a {
  width: 250px;
  font-size: 1.5rem;
  font-weight: 500;
  text-decoration: none;
  color: rgb(25, 25, 25);
  padding: 3rem 1.5rem;
  background-color: rgb(0, 167, 47);
  border-radius: 0.5rem;
  text-align: center;
}

@media (max-width: 570px) {
  .cars a {
    width: 90%;
  }
}
</style>
