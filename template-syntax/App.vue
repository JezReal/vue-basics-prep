<script setup lang="ts">
import { ref } from "vue";

const message = "hello world";
const id = ref("added-class");
const isBoolean = ref(false);
const dynamicId = ref("1");

function coolMessage() {
  return "Cool message";
}

function changeClass() {
  isBoolean.value = !isBoolean.value;
}

function setIdNull() {
  dynamicId.value = null;
}
</script>

<template>
  <div>
    <h1>{{ message }}</h1>
    <h1>{{ coolMessage() }}</h1>
    <h3>{{ 1 + 9 }}</h3>
    <h3>{{ 1 / 9 }}</h3>
    <h3>{{ 1 * 9 }}</h3>

    <div
      class="btn-default"
      v-bind:class="isBoolean ? 'boolean' : 'not-boolean'"
      :id="dynamicId"
    >
      <div>a</div>
      <div>b</div>
      <div>c</div>
    </div>

    <button @click="changeClass">change class</button>
    <button @click="setIdNull">Set id to null</button>
  </div>
</template>

<style scoped></style>
