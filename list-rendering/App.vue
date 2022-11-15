<script setup lang="ts">
import { ref } from "vue";

const data = ref([
  {
    id: 1,
    last_name: "Martin",
    middle_name: "Vinluan",
    first_name: "Jezreel Joshua",
  },
  {
    id: 2,
    last_name: "Doe",
    middle_name: "Smith",
    first_name: "John",
  },
  {
    id: 3,
    last_name: "Hidocos",
    middle_name: "Vinluan",
    first_name: "Jezreel Joshua",
  },
  {
    id: 4,
    last_name: "Vinluan",
    middle_name: "Martin",
    first_name: "Joshua",
  },
  {
    id: 5,
    last_name: "Doa",
    middle_name: "Sam",
    first_name: "Johnny",
  },
]);
</script>

<template>
  <div>
    <h1>List rendering</h1>
    <ul v-for="name in data" :key="name.id">
      <li>
        {{ `${name.last_name}, ${name.first_name} ${name.middle_name[0]} ` }}
      </li>
    </ul>
  </div>
</template>

<style scoped></style>
