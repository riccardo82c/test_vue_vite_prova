<template>
  <div class="flex items-center space-x-3 font-regular ">
    <div class="flex flex-col items-start gap-4">
      <BadgeItem :topic="content.badgeText" :class="`bg-${theme}`"></BadgeItem>
      <h1 class="font-bold max-w-[600px] topic-content-title" :class="[`text-${theme}`, fontSize]">{{ content.caption }}</h1>
      <div class="flex gap-2" :class="`flex-${avatarPosition}`">
        <div class="w-8 h-8 rounded-full bg-gray-400">
          <img :src="content.image" alt="image" class="w-full h-full object-cover rounded-full">
        </div>
        <div class="text-xs my-3" :class="`text-${theme}`">
          <p>{{ content.reporter }}</p>
          <p class="my-3">{{ content.date }}</p>
          <svgIconArrowRight v-if="hasArrow"></svgIconArrowRight>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>

import svgIconArrowRight from '../assets/icons/svg-icon-arrow-right.vue';
import BadgeItem from '@/ui-kit/BadgeItem.vue'

defineProps({
  content: {
    type: Object,
    required: true
  },
  hasArrow: {
    type: Boolean,
    default: true
  },
  avatarPosition: {
    type: String,
    default: 'col'
  },
  theme: {
    type: String,
    default: 'white'
  },
  fontSize: {
    type: String,
    default: ''
  }
})

</script>

<style scoped>
svg {
  fill: white;
}
</style>
