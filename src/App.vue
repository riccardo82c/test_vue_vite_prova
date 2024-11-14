<template>
  <div class="min-h-screen bg-gray-100">
    <Header />

    <section class="container mx-auto">
      <Hero />
      <SubHero />
      <CentralGrid />
      <SubCentralGrid />
      <BlogSection />
      <BottomGrid />
    </section>

    <Header />
  </div>
</template>

<script setup>
import Header from '@/components/Header.vue'
import Hero from './components/Hero.vue';
import SubHero from './components/SubHero.vue';
import CentralGrid from './components/CentralGrid.vue'
import SubCentralGrid from './components/SubCentralGrid.vue';
import BlogSection from './components/BlogSection.vue';
import BottomGrid from './components/BottomGrid.vue';
</script>
