<script setup lang="ts">
import { ref } from "vue";
import type { ArtistWithIdDto } from "./ArtistWithIdDto";
import CustomCard from "./CustomCard.vue";

const artists = ref<ArtistWithIdDto[]>([]);

fetch("https://localhost:7068/api/artists")
  .then((response) => response.json())
  .then((data) => {
    artists.value = data;
  });
</script>

<template>
  <div class="parent">
    <h2>Cool artists</h2>
    <div v-for="artist in artists" :key="artist.id" class="cards">
      <custom-card :artist="artist" />
    </div>
  </div>
</template>

<style scoped>
h2 {
  font-size: 40px;
  text-align: center;
}
.cards {
  width: 75%;
}

.parent {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
