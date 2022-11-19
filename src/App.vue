<script setup lang="ts">
import { ref, watch } from "vue";
import type { ArtistWithIdDto } from "./ArtistWithIdDto";
import CustomCard from "./CustomCard.vue";

const artists = ref<ArtistWithIdDto[]>([]);
let cachedArtists: ArtistWithIdDto[];
const searchTerm = ref<string>("");

watch(searchTerm, (newSearch) => {
  if (newSearch) {
    newSearch = newSearch.trim().toLowerCase();

    artists.value = artists.value.filter((artist) => {
      return artist.artist_name.toLowerCase().includes(newSearch);
    });
  } else {
    artists.value = cachedArtists;
  }
});

fetch("https://localhost:7068/api/artists")
  .then((response) => response.json())
  .then((data) => {
    artists.value = data;
    cachedArtists = data;
  });
</script>

<template>
  <div class="parent">
    <h2>Cool artists</h2>
    <input
      type="text"
      placeholder="Search..."
      name="search_term"
      v-model="searchTerm"
    />

    <div v-if="artists.length > 0" class="cards">
      <div v-for="artist in artists" :key="artist.id">
        <custom-card :artist="artist" />
      </div>
    </div>

    <div v-else>
      <h3>No results found :((</h3>
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
