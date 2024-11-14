<template>
  <div class="grid grid-cols-1 md:grid-cols-3">
    <div v-for="(square, index) in primarySquares" :key="index" class="border-b border-r border-black p-8 md:min-h-72 flex items-end grid-card">
      <div class="">
        <h3 class="text-2xl md:text-5xl font-bold mb-4">{{ square.title }}</h3>
        <p class="">{{ square.description }}</p>
      </div>
    </div>
    <div class="col-span-1 md:col-span-3 grid grid-cols-2 md:grid-cols-6">
      <div v-for="(square, index) in secondarySquares" :key="index + primarySquares.length"
        class="border-r border-black p-4 grid-card">
        <p class="text-center py-8">{{ square.description }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  primarySquares: {
    type: Array,
    required: true
  },
  secondarySquares: {
    type: Array,
    required: true
  }
});
</script>

<style lang="css" scoped>
.grid-card:hover :is(h3, p):first-child {
  @apply cursor-pointer underline;
}
</style>
