<template>
  <v-card
    link
    class="mr-4 mt-2 text-center"
    max-width="200"
    max-height="100"
    min-width="200"
    min-height="100"
    :text=text
    @click="clickingCard"
    variant="outlined"
  ></v-card>
</template>
<script setup>

const props = defineProps({
  text: {
    type: String,
  },
});
const emit = defineEmits(['cardClick'])
const clickingCard = () =>
emit('cardClick',props.text)
</script>
