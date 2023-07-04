<template>
  <v-btn @click="createNewChat" variant="outlined"> + Новый чат </v-btn>
</template>

<script setup>
const props = defineProps({
  createNewChat: {
    type: Function,
  },
});
</script>
