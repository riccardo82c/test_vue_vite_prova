<template>
  <div class="flex items-center px-4 py-12 container text-white h-full relative font-regular">
    <div class="absolute left-12 top-12">
      <img class="object-cover w-full h-full" src="../assets/quote.png" alt="quote">
    </div>
    <div class="ml-32">
      <h3 class="text-2xl md:text-[40px] font-bold">Essere troppo seri non è cosa molto seria</h3>
      <h4 class="font-semibold pt-4"><i>[ Detto Africano ]</i></h4>
    </div>
  </div>
</template>

<script setup>

import svgIconArrowRight from '../assets/icons/svg-icon-arrow-right.vue';
</script>

<style lang="css" scoped>
.container {
  background: url('../assets/sub_central_grid_img.png');
  background-position: center;
  background-size: cover;

}
</style>
