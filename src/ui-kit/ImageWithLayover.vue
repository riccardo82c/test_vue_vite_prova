<template>

  <div class="relative image-layover-container overflow-hidden">
    <slot name="image"></slot>
    <div class="absolute inset-0 bg-gray-800" :class="layoverOpacity"></div>
    <div class="absolute text-white text-left" :class="layoverPositionClasses">
      <slot name="layover"></slot>
    </div>
  </div>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  layoverPositionClasses: {
    type: String,
    default: 'bottom-4 left-4', // Posizione di default
  },
  layoverOpacity: {
    type: String,
    default: 'bg-opacity-50', // Opacità di default
  },
})
</script>

<style scoped>
.relative {
  position: relative;
}

.absolute {
  position: absolute;
}

.inset-0 {
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
}

.bottom-4 {
  bottom: 1rem;
}

.left-4 {
  left: 1rem;
}

.text-white {
  color: #ffffff;
}

.text-left {
  text-align: left;
}

.image-layover-container {
  container-type: inline-size;
}

:deep(.topic-content-title) {

  @container (min-width: 200px) {
    font-size: 22px;
    line-height: 32px;
  }

  @container (min-width: 600px) {
    font-size: 30px;
    line-height: 46px;
  }

  @container (min-width: 800px) {
    font-size: 38px;
    line-height: 54px;
  }
}
</style>
