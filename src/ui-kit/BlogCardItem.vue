<template>
  <div class="flex-auto flex flex-col items-center justify-center text-center border-2 p-4 w-40 space-y-2 font-regular">
    <Avatar v-if="image" :src="image" size="large" />
    <h3 class="font-bold text-lg" :class="customClass" v-if="title">{{ title }}</h3>
    <p class="text-gray-500" v-if="author">{{ author }}</p>
  </div>
</template>

<script setup>
import Avatar from './Avatar.vue';

const props = defineProps({
  image: {
    type: String,
    required: false
  },
  title: {
    type: String,
    required: true
  },
  author: {
    type: String,
    required: false
  },
  customClass: {
    type: String,
    required: false
  }
});
</script>

<style scoped>
/* Stili specifici per la card, se necessari */
</style>
