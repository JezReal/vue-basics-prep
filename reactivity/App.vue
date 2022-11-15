<script setup lang="ts">
import { computed, reactive, ref } from "vue";

const message = ref("Goodbye cruel world");

const coolObject = reactive({
  id: 1,
  name: "Jezryl",
});

const anotherObJect = ref({
  id: 2,
  name: "JezReal",
});

const inputValue = ref("");

const errorMessage = computed(function () {
  if (inputValue.value.length < 10) {
    return "Ten minimum characters!";
  }

  return "You pass";
});

function changeText() {
  message.value = "Hello cruel world";
}

function resetText() {
  message.value = "Goodbye cruel world";
}

function updateCoolObjectName() {
  coolObject.name = "Jezryl updated";
}

function updateAnotherObjectName() {
  anotherObJect.value.name = "JezReal updated";
}
</script>

<template>
  <div>
    <h1>{{ message }}</h1>
    <button @click="changeText">Change text</button>
    <button v-on:click="resetText">reset</button>

    <h3>{{ coolObject.name }}</h3>
    <button @click="updateCoolObjectName">Update name</button>
    <br />

    <h3>{{ anotherObJect.name }}</h3>
    <button @click="updateAnotherObjectName">Update another name</button>

    <br />
    <br />

    <h3>{{ inputValue }}</h3>
    <input type="text" placeholder="Enter text" v-model="inputValue" />
    <h3>{{ errorMessage }}</h3>
  </div>
</template>

<style scoped></style>
