<template>
  <div class="grid grid-cols-4">
    <!-- Primo riquadro -->
    <div class="h-[470px] col-span-4">
      <ImageWithLayover class="h-full" layoverPositionClasses="left-4 top-14">
        <template #image>
          <img class="object-cover w-full h-full" :src="mappedPathContent[0].src" alt="">
        </template>
        <template #layover>
          <TopicContent :content="content[0]" fontSize="small"></TopicContent>
        </template>
      </ImageWithLayover>
    </div>

    <!-- Secondo riquadro -->
    <div class="h-[370px]">
      <ImageWithLayover class="h-full" layoverPositionClasses="left-4 top-14" layoverOpacity="bg-opacity-0">
        <template #image>
          <div class="w-full h-full bg-white"></div>
        </template>
        <template #layover>
          <TopicContent :content="content[1]" theme="black" fontSize="small"></TopicContent>
        </template>
      </ImageWithLayover>
    </div>

    <!-- Terzo riquadro -->
    <div class="h-[370px]">
      <ImageWithLayover class="h-full" layoverPositionClasses="left-4 top-14">
        <template #image>
          <img class="object-cover w-full h-full" :src="mappedPathContent[2].src" alt="">
        </template>
        <template #layover>
          <TopicContent :content="content[2]" fontSize="small"></TopicContent>
        </template>
      </ImageWithLayover>
    </div>

    <!-- Quarto riquadro -->
    <div class="h-[370px]">
      <ImageWithLayover class="h-full" layoverPositionClasses="left-4 top-14" layoverOpacity="bg-opacity-0">
        <template #image>
          <div class="w-full h-full bg-red-600"></div>
        </template>
        <template #layover>
          <TopicContent :content="content[3]" fontSize="small"></TopicContent>
        </template>
      </ImageWithLayover>
    </div>

    <!-- Quinto riquadro -->
    <div class="h-[370px]">
      <ImageWithLayover class="h-full" layoverPositionClasses="right-4 top-14">
        <template #image>
          <img class="object-cover w-full h-full" :src="mappedPathContent[4].src" alt="">
        </template>
        <template #layover>
          <TopicContent :content="content[4]" class="max-w-[500px]" fontSize="small"></TopicContent>
        </template>
      </ImageWithLayover>
    </div>
  </div>

  <div class="grid grid-cols-2">
    <!-- Primo riquadro -->
    <div>
      <div class="grid grid-rows-4">
        <div class="h-[180px]">
          <ImageWithLayover class="h-full" layoverPositionClasses="left-4 top-14">
            <template #image>
              <img class="object-cover w-full h-full" :src="mappedPathContent[5].src" alt="">
            </template>
            <template #layover>
              <TopicContent :content="content[5]" fontSize="small"></TopicContent>
            </template>
          </ImageWithLayover>
        </div>
        <div class="h-[180px]">
          <ImageWithLayover class="h-full" layoverPositionClasses="left-4 top-14">
            <template #image>
              <img class="object-cover w-full h-full" :src="mappedPathContent[6].src" alt="">
            </template>
            <template #layover>
              <TopicContent :content="content[6]" fontSize="small"></TopicContent>
            </template>
          </ImageWithLayover>
        </div>
        <div class="h-[180px]">
          <ImageWithLayover class="h-full" layoverPositionClasses="left-4 top-14">
            <template #image>
              <img class="object-cover w-full h-full" :src="mappedPathContent[7].src" alt="">
            </template>
            <template #layover>
              <TopicContent :content="content[7]" fontSize="small"></TopicContent>
            </template>
          </ImageWithLayover>
        </div>
        <div class="h-[180px]">
          <ImageWithLayover class="h-full" layoverPositionClasses="left-4 top-14">
            <template #image>
              <img class="object-cover w-full h-full" :src="mappedPathContent[8].src" alt="">
            </template>
            <template #layover>
              <TopicContent :content="content[8]" fontSize="small"></TopicContent>
            </template>
          </ImageWithLayover>
        </div>
      </div>
    </div>


    <!-- Secondo riquadro -->
    <div>
      <ImageWithLayover class="h-full" layoverPositionClasses="left-4 top-14">
        <template #image>
          <img class="object-cover w-full h-full" :src="mappedPathContent[9].src" alt="">
        </template>
        <template #layover>
          <TopicContent :content="content[9]"></TopicContent>
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
    src: 'image9.jpeg',
    alt: '',
    badgeText: 'IMPRESA SOCIALE',
    caption: 'La Kasbah mazarese nella quale si gusta la cultura araba',
    avatar: 'avatar_1.png',
    reporter: 'Di Giovanni Gavardi',
    date: '3 Luglio 2022 '
  },
  {
    id: 2,
    src: '',
    alt: '',
    badgeText: 'SPONSORED',
    caption: 'Sostenibilità sociale: accordo tra Dynamo Academy e Acsi',
    avatar: 'avatar_2.png',
    reporter: 'Di Dynamo Academy',
    date: '13 luglio 2022'
  },
  {
    id: 3,
    src: 'image10.jpeg',
    alt: '',
    badgeText: 'PERSONE',
    caption: "Uccisa ad Haiti suor Luisa, era l'angelo dei bambini",
    avatar: 'avatar_3.png',
    reporter: 'Di Lucia Capuzzi',
    date: '1 Luglio 2022 '
  },
  {
    id: 4,
    src: '',
    alt: '',
    badgeText: 'SPORT',
    caption: 'Troppi abusi nello sport: minorile, il governo interviene con loro riparte l"Italia',
    avatar: 'avatar_4.png',
    reporter: 'Di Redazione',
    date: '13 luglio 2022'
  },
  {
    id: 5,
    src: 'image11.jpeg',
    alt: '',
    badgeText: 'NETWORKING',
    caption: "Il fundraising in rotta verso Giardini-Naxos",
    avatar: 'avatar_5.png',
    reporter: 'Di Redazione',
    date: '13 luglio 2022'
  },
  {
    id: 6,
    src: 'image12.jpeg',
    alt: '',
    badgeText: 'SOCIETÀ CIVILE',
    caption: "Lisa, il modello Croce Rossa per l'inclusione lavorativa",
    avatar: 'avatar_6.png',
    reporter: 'Di Francesco Palazzo',
    date: '13 luglio 2022'
  },
  {
    id: 7,
    src: 'image13.jpeg',
    alt: '',
    badgeText: 'INNOVAZIONE',
    caption: 'Gli anziani del Sicomoro spopolano su TikTok',
    avatar: 'avatar_7.png',
    reporter: 'Di Redazione',
    date: '13 luglio 2022'
  },
  {
    id: 8,
    src: 'image14.jpeg',
    alt: '',
    badgeText: 'DISABILITÀ',
    caption: '"Emergenza sordi": quando un\'app ti salva la vita',
    avatar: 'avatar_8.png',
    reporter: 'Di Sara Bellingeri',
    date: '13 luglio 2022'
  },
  {
    id: 9,
    src: 'image15.jpeg',
    alt: '',
    badgeText: 'TRAIETTORIE',
    caption: 'Diego, il fruttivendolo che ha scelto la cooperazione sociale',
    avatar: 'avatar_8.png',
    reporter: 'Di Redazione',
    date: '13 luglio 2022'
  },
  {
    id: 10,
    src: 'image16.png',
    alt: '',
    badgeText: 'UCRAINA',
    caption: 'Leopoli, andata + ritorno',
    avatar: 'avatar_8.png',
    reporter: 'Di Giovanni Gamba',
    date: '13 luglio 2022'
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
