<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import Galleria from 'primevue/galleria';
import ImpactLogo from "@/assets/ImpactLogo.jpg";
import SourceLogo from "@/assets/SourceLogo.png";
import Slider from "@/components/Slider.vue"
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
  <Slider />

  <RouterView />
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
