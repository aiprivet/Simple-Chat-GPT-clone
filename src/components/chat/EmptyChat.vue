<template>
  <v-container class="justify-space-between container" :class="{
    
  }">
    <LogoEmpty class="mt-14"/>
    <v-row style="margin-top: 230px;" class="  justify-center">
      <SampleCard 
      class="d-none d-sm-block"

        text="Напиши историю про кота ,цепочкой смайликов🐱"
        @cardClick="handleCardClick" />
      <SampleCard
      class="d-none d-sm-block"

        text="Напиши краткое содержание книги «Война и Мир».📖"
        @cardClick="handleCardClick"
      />
      <SampleCard
        text="Переведи с русского на китайский текст «Где моя посылка?».🇨🇳 "
        @cardClick="handleCardClick"
      />
    </v-row>
    <v-row class="mt-4 justify-center" >
      <SampleCard
      class="d-none d-sm-block"
        text=" Составь резюме для python-программиста без опыта работы. 💼"
        @cardClick="handleCardClick"
      />
      <SampleCard 
      class="d-none d-sm-block"
      text=" Опишите ужасное похмелье, языком крестьянина 18 века.👨🏻‍🌾  " 
      @cardClick="handleCardClick"/>
      <SampleCard 
      class="d-none d-sm-block"

      text=" Напиши на javascript функцию сортировки массива объектов.♻️" 
      @cardClick="handleCardClick"
      />
    </v-row>
  </v-container>
</template>
<script setup>
import LogoEmpty from "./LogoEmpty.vue";
import SampleCard from "./SampleCard.vue";
import { useDisplay } from 'vuetify'
const { mobile } = useDisplay()
const props = defineProps({
  text: {
    type: String,
  },
});
const emit = defineEmits(["cardClick"]);
const handleCardClick = (cardText) => {
  emit('cardClick', cardText);
}

</script>
<style>

</style>
