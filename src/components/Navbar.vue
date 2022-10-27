<template>
  <div class="navbar-container">
    <div class="item" v-for="item in navBarItems" :key="item.title" :class="{active: itemActive === item.title}">
      <router-link :to="item.path" @click="changeCurrentItem(item.title)"> {{ item.title }} </router-link>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";

const navBarItems = ref([
  { title: "Accueil", path: "/" },
  { title: "Projects de Game Design", path: "/game-design" },
  { title: "CV", path: "/about" },
  { title: "Contact", path: "/contact" }
])

const itemActive = ref("Accueil")

const changeCurrentItem = (title: string) => {
  itemActive.value = title
}
</script>

<style scoped lang="scss">
.navbar-container {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 30px;
  height: 50px;
  margin-bottom: 20px;
}

.item {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 0 20px;
  height: 100%;
  border-radius: 50px;

  a {
    color: black;
    text-decoration: none;
  }
  &:hover {
    background-color: #8d99ae;
  }
}

.active {
  background-color: #8d99ae;
}
</style>