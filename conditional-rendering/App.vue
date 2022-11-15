<script setup lang="ts">
import { ref } from "vue";

const something = ref(false);
</script>

<template>
  <div>
    <h1 v-show="something">If block</h1>
    <!-- <h1 v-else>else block</h1> -->
  </div>
</template>

<style scoped></style>
