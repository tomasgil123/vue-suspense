<template>
  <div>
    BreedList
    <div v-for="breed in breedsList" :key="breed">Test{{ breed }}</div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  name: "BreedList",
  async setup() {
    const breedsList = ref([]);
    const breeds = await (
      await fetch("https://dog.ceo/api/breeds/list/all")
    ).json();
    breedsList.value = Object.keys(breeds.message);
    return { breedsList };
  }
};
</script>
