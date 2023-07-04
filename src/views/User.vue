<template>
  <v-menu min-width="200px">
    <template v-slot:activator="{ props }">
      <v-btn icon v-bind="props">
        <v-avatar size="35"
          ><v-icon class="hover" v-if="keyEntered === false">
            mdi-account-circle
          </v-icon>
          <v-icon color="primary" v-if="keyEntered"> mdi-account-check </v-icon>
        </v-avatar>
      </v-btn>
    </template>
    <v-card>
      <v-card-title class="bg-black text-caption">⚙️ Настройки</v-card-title>
      <v-card-text>
        <br />
        <div class="mx-auto text-center mb-3">
          <haveKey v-if="keyEntered" />
          <noKey v-else />

          <v-divider v-if="keyEntered === false" class="my-2" />
          <EnterKey v-if="keyEntered === false" />
          <v-divider v-if="keyEntered === false" class="my-2" />

          <v-btn @click="deleteAllChats" color="red" variant="text">
            Сбросить все настройки ❌</v-btn
          >
        </div>
      </v-card-text>
    </v-card>
  </v-menu>
</template>
<script setup>
import EnterKey from "@/components/user/EnterKey.vue";
import noKey from "@/components/user/noKey.vue";
import haveKey from "@/components/user/haveKey.vue";
import { ref } from "vue";

const keyEntered = ref(JSON.parse(localStorage.getItem("keyEntered")) || false);

const deleteAllChats = () => {
  localStorage.clear();
  location.reload();
};
</script>
<style>
.hover {
}
.hover:hover {
  color: rgb(205, 134, 255);
}
</style>
