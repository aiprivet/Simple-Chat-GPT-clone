<template>
  <v-text-field
    auto-grow
    variant="outlined"
    class="align-center field"
    rows="1"
    max-rows="3"
    color="tonal"
    @keypress.enter.prevent.stop="send()"
  >
    <template  v-slot:append-inner>
      <v-icon class="hover" @click.prevent.stop="send" color="tonal"> mdi-send </v-icon>
    </template>
  </v-text-field>
</template>
<script setup>
const props = defineProps({
  send: {
    type: Function,
  },
});



</script>

<style>
.field {
  margin: 0 auto;
  max-width: 900px;
}
.hover{

}
.hover:hover{
color: rgb(205, 134, 255);
}
</style>
