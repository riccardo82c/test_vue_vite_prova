<template>
  <header class="container mx-auto bg-white ">
    <div class=" mx-auto flex justify-between  px-10 py-4 font-regular text-sm">
      <div class="flex gap-4">
        <span class="link">Contribuisci</span>
        <span class="link">Abbonati</span>
      </div>
      <div class="flex gap-4 items-center">
        <span class="link">Accedi</span>
        <svgIconUser />
      </div>
    </div>
    <div class="flex justify-between items-center border-y border-black h-16">
      <div class="flex items-center h-full px-4 border-r border-black ">
        <button @click="toggleMenu" class="focus:outline-none ">
          <svgIconBurgherOpen v-if="!isMenuOpen"/>
          <svgIconBurgherClose v-else/>
        </button>
      </div>
      <div class="flex items-center h-full px-4 border-l border-black ">

        <svgIconSearch />
      </div>
    </div>

    <!-- Dropdown Menu -->
    <div class="relative">
      <div class="absolute w-full bg-white shadow-lg overflow-hidden transition-all duration-300 ease-in-out z-10"
        :class="isMenuOpen ? 'max-h-[1000px] opacity-100' : 'max-h-0 opacity-0'">
        <SubMenuGrid
          :primarySquares
          :secondarySquares
        >
        </SubMenuGrid>
      </div>
    </div>
  </header>
</template>

<script setup>
import { ref } from 'vue'
import svgIconUser from '@/assets/icons/svg-icon-user.vue';
import svgIconBurgherOpen from '@/assets/icons/svg-icon-burgher-open.vue';
import svgIconBurgherClose from '@/assets/icons/svg-icon-burgher-close.vue';
import svgIconSearch from '@/assets/icons/svg-icon-search.vue';
import SubMenuGrid from '@/components/SubMenuGrid.vue';

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const primarySquares = [
  {
    title: "Articoli",
    description: "Trend, dati e novità del Terzo Settore."
  },
  {
    title: "Storie",
    description: "Letture ed approfondimenti dei fenomeni complessi."
  },
  {
    title: "Interviste",
    description: "Racconti reali di persone ed organizzazioni."
  },
  {
    title: "Opinioni",
    description: "Riflessioni e confronti dei nostri opinionisti."
  },
  {
    title: "Podcast",
    description: "Un luogo per dare voce ai protagonisti della sostenibilità."
  },
  {
    title: "Bookazine",
    description: "Una rivista da leggere e un libro da conservare."
  }
]

const secondarySquares = [
  {
    description: "Chi siamo"
  },
  {
    description: "Comitato editoriale"
  },
  {
    description: "Servizi"
  },
  {
    description: "Agenda / Eventi"
  },
  {
    description: "Mappa dell’attivismo"
  },
  {
    description: "Inchieste crowdfunding"
  }
]
</script>

<style scoped>
.max-h-64 {
  max-height: 32rem;
}
</style>
