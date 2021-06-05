<template>
  <div class="p-grid p-jc-around">
    <div class="p-col-12 p-md-6 p-lg-3" v-for="pet in pets" :key="pet.id">
      <!-- <h3>{{ pet.name }}</h3> -->
      <Pet
        @remove-pet="$emit('remove-pet', pet.id)"
        @add-favorite="$emit('add-favorite', pet.id)"
        :pet="pet"
      />
    </div>
  </div>
</template>

<script>
import Pet from "./Pet";

export default {
  props: {
    pets: Array,
  },
  components: { Pet },
  emits: ["remove-pet", "add-favorite"],
};
</script>

<style></style>
