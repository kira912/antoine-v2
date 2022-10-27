<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import ImpactLogo from "@/assets/ImpactLogo.jpg";
import SourceLogo from "@/assets/SourceLogo.png";

import Navbar from "@/components/Navbar.vue"
import { ref } from "vue";

const images = ref([
  {
    "itemImageSrc": ImpactLogo,
    "alt": "Description for Image 1",
    "title": "Title 1"
  },
  {
    "itemImageSrc": SourceLogo,
    "alt": "Description for Image 2",
    "title": "Title 2"
  },
])
</script>

<template>
  <div class="container">
    <h1>Antoine de Seguins</h1>
    <h2>Game Designer Junior</h2>
  </div>
  <Navbar />
  <RouterView />
</template>

<style scoped lang="scss">
#app, html {
  font-family: 'Helvetica 55Roman';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

h1 {
  margin: 0;
  font-size: 50px;
}
</style>
