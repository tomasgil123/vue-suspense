<template>
  <div class="home">
    <div>Title</div>
    <Suspense>
      <template #default>
        <BreedList />
      </template>
      <template #fallback>
        <span>Loading...</span>
      </template>
    </Suspense>
  </div>
</template>

<script>
import BreedList from "@/components/BreedList";

export default {
  name: "Home",
  components: {
    BreedList
  }
};
</script>
