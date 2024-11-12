<template>
  <div
    :class="[
      'rounded-full overflow-hidden flex items-center justify-center',
      sizeClass
    ]"
  >
    <img
      :src="src"
      alt="Avatar"
      class="object-cover w-full h-full"
    />
  </div>
</template>

<script setup>
import { defineProps, computed } from 'vue';

const props = defineProps({
  src: {
    type: String,
    required: true
  },
  size: {
    type: String,
    default: 'standard',
    validator: value => ['standard', 'large'].includes(value)
  }
});

const sizeClass = computed(() => (props.size === 'large' ? 'w-[84px] h-[84px]' : 'w-[48px] h-[48px]')); // 84px e 48px
</script>
