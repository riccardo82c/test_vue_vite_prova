<template>

  <div class="flex min-h-[200px]">
    <BlogCardItem v-for="item, index in mappedPathContent" :key="index" :image="item.src" :title="item.title"
      :author="item.author" :customClass="item.customClass" />
  </div>
</template>

<script setup>
import { computed } from 'vue'

import BlogCardItem from '@/ui-kit/BlogCardItem.vue'

const blogItems = [
  { title: "Il Blog", customClass: "text-[40px] text-red-600" },
  { src: 'blog1.jpeg', title: "Il Becco dell'oca", author: 'Di Paolo Dell’Oca' },
  { src: 'blog1.jpeg', title: 'Disarmato', author: 'Di Pasquale Pugliese' },
  { src: 'blog1.jpeg', title: 'Battitiperminuto', author: 'Di Lorenzo Maria Alvaro' },
  { src: 'blog1.jpeg', title: 'La Zanzarella', author: 'Di Elena Zanella' },
  { src: 'blog1.jpeg', title: 'Impact Q&A', author: 'Di Laura Orestano' },
]

const mappedPathContent = computed(() => {
  return blogItems.map((blogItem) => {

    return {
      ...blogItem,
      src: blogItem.src && new URL(`../assets/avatar/${blogItem.src}`, import.meta.url).href
    }
  })
})

</script>

<style scoped></style>
