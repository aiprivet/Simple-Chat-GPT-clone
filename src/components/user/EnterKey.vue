<template>
  <v-snackbar v-model="alert" multi-line location="top" color="error">
    ❌ Неверный API-ключ !
    <template v-slot:actions>
      <v-btn color="red" variant="text" @click="alert = false"> Закрыть </v-btn>
    </template>
  </v-snackbar>

  <v-btn color="primary" variant="text">
    Ввести API-ключ 🔑
    <v-dialog v-model="dialog" activator="parent" width="auto">
      <v-card max-width="400">
        <v-card-title class="bg-black text-caption"
          >🔑 Введите API-ключ</v-card-title
        >

        <v-card-text class="mx-auto">
          <v-avatar size="35" class="mx-auto d-flex"
            ><v-icon
              icon="mdi-key-alert-outline"
              color="primary"
              size="x-large"
            ></v-icon
          ></v-avatar>

          <br />

          <p class="text-center mx-auto multi-line">
            Для работы приложения необходимо ввести API-ключ, вы можете ввести
            ключ ниже
          </p>
          <br />
        </v-card-text>
        <v-textarea
          focused
          v-model="api"
          class="mx-8"
          no-resize
          rows="1"
          variant="solo-filled"
          placeholder="Введите API-ключ"
        >
        </v-textarea>
        <v-btn
          @click="enterKey"
          color="primary"
          size="large"
          class="mx-auto mb-4"
          variant="solo-filled"
          >Ввести ключ 🔑</v-btn
        >
      </v-card>
    </v-dialog>
  </v-btn>
</template>
<script setup>
import { ref } from "vue";
const alert = ref(false);
const dialog = ref(false);
const api = ref(localStorage.getItem("api"));
const enterKey = () => {
  if (api.value.length > 48 && api.value.startsWith("sk-")) {
    localStorage.setItem("api", JSON.stringify(api.value));
    localStorage.setItem("keyEntered", JSON.stringify(true));
    dialog.value = false;
    window.location.reload();
    alert.value = true;
  } else {
    alert.value = true;
  }
};
</script>
