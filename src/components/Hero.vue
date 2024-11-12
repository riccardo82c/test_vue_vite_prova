<template>
  <div class="font-regular">
    <nav class="flex items-center justify-between px-4 py-16">
      <div class="text-2xl md:text-5xl font-bold">Tutti i temi</div>
      <div class="flex space-x-2">
        <div v-for="topic in topics" :key="topic" class="px-3 py-1 rounded-full text-sm">
          <ButtonItem :topic="topic.label" :class="[topic.class, 'font-display', 'text-xs', 'h-16']"></ButtonItem>
        </div>
      </div>
    </nav>

    <div class="grid">

      <ImageWithLayover>
        <template #image>
          <img class="object-cover object-center max-h-[500px] w-full " :src="mappedPathContent[0].src" alt="">
        </template>
        <template #layover>
          <TopicContent  :content="content[0]" :avatarPosition="'row'" :hasArrow="false"></TopicContent>
        </template>
      </ImageWithLayover>

      <div class="grid grid-cols-[3fr_2fr]">

        <ImageWithLayover>
          <template #image>
            <img class="object-cover object-center h-full w-full " :src="mappedPathContent[1].src" alt="">
          </template>
          <template #layover>
            <TopicContent  :content="content[1]"></TopicContent>
          </template>
        </ImageWithLayover>

        <div>

          <ImageWithLayover>
            <template #image>
              <img class="h-auto max-w-full " :src="mappedPathContent[2].src" alt="">
            </template>
            <template #layover>
              <TopicContent  :content="content[2]"></TopicContent>
            </template>
          </ImageWithLayover>

          <ImageWithLayover>
            <template #image>
              <img class="h-auto max-w-full " :src="mappedPathContent[3].src" alt="">
            </template>
            <template #layover>
              <TopicContent  :content="content[3]"></TopicContent>
            </template>
          </ImageWithLayover>

        </div>

      </div>
    </div>



  </div>
</template>

<script setup>
import { computed } from 'vue';

import ButtonItem from '@/ui-kit/ButtonItem.vue';
import TopicContent from '@/components/TopicContent.vue';
import ImageWithLayover from '../ui-kit/ImageWithLayover.vue';

const topics = [
  {
    label: 'Ambiente',
    class: 'bg-red-200'
  },
  {
    label: 'Economia',
    class: 'bg-green-200'
  },
  {
    label: 'Mondo',
    class: 'bg-blue-200'
  },
  {
    label: 'San Pietro',
    class: 'bg-yellow-200'
  },
  {
    label: 'Politica',
    class: 'bg-purple-200'
  },
  {
    label: 'Società',
    class: 'bg-pink-200'
  },
  {
    label: 'Vaticano',
    class: 'bg-indigo-200'
  }
]

const content = [
  {
    id: 1,
    src: 'image1.jpeg',
    // src: new URL('@/assets/image1.jpeg', ).href,
    alt: 'Image 1',
    badgeText: 'MIGRANTI',
    caption: 'Roccella Jonica, la Lampedusa che l\'Italia ignora',
    avatar: 'avatar1.png',
    reporter: 'Alessandro Puglia',
    date: '29 giugno 2022'
  },
  {
    id: 2,
    src: 'image2.png',
    alt: 'Image 2',
    badgeText: 'ALLARMI',
    avatar: 'avatar2.png',
    caption: 'Il collasso dei ghiacciai negli scatti del fotografo ambientale Fabiano Ventura',
    reporter: 'Ugo Lombi',
    date: '14 luglio 2022'
  },
  {
    id: 3,
    src: 'image3.jpeg',
    alt: 'Image 3',
    badgeText: 'ESPERIMENTI',
    avatar: 'avatar3.png',
    caption: 'Gli star-upper? Li trovi al bistrot. Così il Dumbo incuba relazioni',
    reporter: 'Diletta Grella',
    date: '14 luglio 2022'

  },
  {
    id: 4,
    src: 'image4.png',
    alt: 'Image 4',
    badgeText: 'UCRAINA',
    avatar: 'avatar4.png',
    caption: 'Nelle città italiane tutti in piazza per e con Kiev',
    reporter: 'Anna Spena',
    date: '14 luglio 2022'

  },
]

const mappedPathContent = computed(() => {
  return content.map((item) => {
    return {
      ...item,
      src: new URL(`../assets/${item.src}`, import.meta.url).href
    }
  })
})

</script>
