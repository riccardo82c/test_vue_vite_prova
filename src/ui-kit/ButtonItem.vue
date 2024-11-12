<template>
  <button
    class="uppercase text-black font-bold px-6 py-3 rounded-lg topic-shadow hover:shadow-none transition-shadow duration-200 border-2 border-black">
    {{ topic }}
  </button>
</template>


<script setup>

defineProps({
  topic: {
    type: String,
    required: true
  }
})


</script>
