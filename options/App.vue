<script setup lang="ts">
import { ref } from "vue";

// export default {
//   data() {
//     return {
//       count: 1,
//     };
//   },
//   methods: {
//     increment() {
//       this.count++;
//     },
//   },
// };

const count = ref(1);

function increment() {
  count.value++;
}
</script>

<template>
  <div>
    <h1>Count: {{ count }}</h1>
    <button @click="increment">Increment</button>
  </div>
</template>

<style scoped></style>
