<template>
  <span
    class="uppercase text-black font-semibold px-2 text-[10px] rounded-sm badge-shadow border border-black">
    {{ topic }}
  </span>
</template>


<script setup>

defineProps({
  topic: {
    type: String,
    required: true
  }
})


</script>
