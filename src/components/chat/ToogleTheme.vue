<template>

<v-btn class="mr-4 text-h5" icon @click="toggleTheme">
        {{ currentTheme === "dark" ? "🌙" : "☀️" }}
      </v-btn>
</template>

<script setup>

  import { useTheme } from 'vuetify';
  
  const theme = useTheme();
  
  theme.global.name.value = localStorage.getItem("theme") || "dark";
  
  let currentTheme = theme.global.name.value;
  
  const toggleTheme = () => {
    theme.global.name.value = theme.global.current.value.dark ? "light" : "dark";
    localStorage.setItem("theme", theme.global.name.value);
    currentTheme = localStorage.getItem("theme");
    window.location.reload()
  };
  
</script>