<template>
  <div class="grid grid-cols-3">
    <!-- Primo riquadro -->
    <div class="h-[440px]">
      <ImageWithLayover class="h-full" layoverPositionClasses="left-4 top-14" layoverOpacity="bg-opacity-0">
        <template #image>
          <div class="w-full h-full bg-red-600"></div>
          <!-- <img class="object-cover w-full h-full" :src="mappedPathContent[0].src" alt=""> -->
        </template>
        <template #layover>
          <TopicContent :content="content[0]"></TopicContent>
        </template>
      </ImageWithLayover>
    </div>

    <!-- Secondo riquadro -->
    <div class="h-[440px]">
      <ImageWithLayover class="h-full" layoverPositionClasses="left-4 top-14">
        <template #image>
          <img class="object-cover w-full h-full" :src="mappedPathContent[1].src" alt="">
        </template>
        <template #layover>
          <TopicContent :content="content[1]"></TopicContent>
        </template>
      </ImageWithLayover>
    </div>

    <!-- Terzo riquadro -->
    <div class="h-[440px]">
      <ImageWithLayover class="h-full" layoverPositionClasses="left-4 top-14">
        <template #image>
          <img class="object-cover w-full h-full" :src="mappedPathContent[2].src" alt="">
        </template>
        <template #layover>
          <TopicContent :content="content[2]"></TopicContent>
        </template>
      </ImageWithLayover>
    </div>

    <!-- Quarto riquadro -->
    <div class="h-[440px]">
      <ImageWithLayover class="h-full" layoverPositionClasses="left-4 top-14">
        <template #image>
          <img class="object-cover w-full h-full" :src="mappedPathContent[3].src" alt="">
        </template>
        <template #layover>
          <TopicContent :content="content[3]"></TopicContent>
        </template>
      </ImageWithLayover>
    </div>

    <!-- Quinto riquadro (quello grande) -->
    <div class="h-[440px] col-span-2">
      <ImageWithLayover class="h-full" layoverPositionClasses="right-4 top-14">
        <template #image>
          <img class="object-cover w-full h-full" :src="mappedPathContent[4].src" alt="">
        </template>
        <template #layover>
          <TopicContent :content="content[4]" class="max-w-[500px]"></TopicContent>
        </template>
      </ImageWithLayover>
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
    src: '',
    alt: '',
    badgeText: 'ODESSA',
    caption: '“Qui Odessa”: fotografie, progetti e solidarietà',
    avatar: 'avatar_x.png',
    reporter: 'Di Redazione',
    date: '13 luglio 2022'
  },
  {
    id: 2,
    src: 'image5.jpeg',
    alt: 'Image 2',
    badgeText: 'VIOLENZA',
    caption: 'Storie fra ragazze: permetteteci di violenza. A Napoli 12enne sfregiata da 12enne',
    avatar: 'avatar_5.png',
    reporter: 'Di Giulia Savarelli',
    date: '13 luglio 2022'
  },
  {
    id: 3,
    src: 'image6.jpeg',
    alt: 'Image 3',
    badgeText: 'LAVORO',
    caption: '“Co-agitiamo”: Teggiano una cooperativa di comunità contro lo spopolamento',
    avatar: 'avatar_6.png',
    reporter: 'Di Anna Spena',
    date: '12 luglio 2022'
  },
  {
    id: 4,
    src: 'image7.jpeg',
    alt: 'Image 4',
    badgeText: 'SPORT',
    caption: 'Troppi abusi nello sport: minorile, il governo interviene',
    avatar: 'avatar_7.png',
    reporter: 'Di Riccardo Maffei',
    date: '7 luglio 2022'
  },
  {
    id: 5,
    src: 'image8.jpeg',
    alt: 'Image 5',
    badgeText: 'INTERVISTA',
    caption: 'Donne e nuove generazioni: con loro riparte l’Italia',
    avatar: 'avatar_8.png',
    reporter: 'Di Tiziana Bagnato',
    date: '7 luglio 2022'
  }
];


const mappedPathContent = computed(() => {
  return content.map((item) => {
    return {
      ...item,
      src: new URL(`../assets/${item.src}`, import.meta.url).href
    }
  })
})

</script>
