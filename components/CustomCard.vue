<script setup lang="ts">
const props = defineProps<{
  message: string;
}>();
</script>

<template>
  <div>
    <h2>This is a {{ props.message }} component</h2>
  </div>
</template>

<style scoped></style>
