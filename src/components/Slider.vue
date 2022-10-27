<template>
<!--  <div class="swiper-container">-->
<!--    <div class="swiper-wrapper">-->
<!--      <div class="swiper-slide">-->
<!--        <div class="container-general">-->
<!--          <div class="gallery-wrap wrap-effect-1">-->
<!--            <img class="item" src="@/assets/ImpactLogo.jpg" />-->
<!--            <img class="item" src="@/assets/AjustLogo.jpg" />-->
<!--            <img class="item" src="@/assets/ArupLogo.jpg" />-->
<!--            <img class="item" src="@/assets/DoughLogo.jpg" />-->
<!--            <img class="item" src="@/assets/SourceLogo.png" />-->
<!--            <img class="item" src="@/assets/VahanaLogo.png" />-->
<!--            <img class="item" src="@/assets/ProteoLogo.png" />-->
<!--          </div>-->
<!--        </div>-->
<!--      </div>-->
<!--    </div>-->
<!--  </div>-->
  <div>
    <transition-group name='fade' tag='div'>
      <div v-for="i in [currentIndex]" :key='i'>
        <img :src="currentImg" />
      </div>
    </transition-group>
    <a class="prev" @click="prev" href='#'>&#10094;</a>
    <a class="next" @click="next" href='#'>&#10095;</a>
  </div>
</template>

<script setup lang="ts">
import {
  computed,
  ref
} from "vue";
import ImpactLogo from "@/assets/ImpactLogo.jpg";
import AjustLogo from "@/assets/AjustLogo.jpg";
import ArupLogo from "@/assets/ArupLogo.jpg";
import DoughLogo from "@/assets/DoughLogo.jpg";
import SourceLogo from "@/assets/SourceLogo.png";
import VahanaLogo from "@/assets/VahanaLogo.png";
import ProteoLogo from "@/assets/ProteoLogo.png";
const images = ref([
  ImpactLogo,
  AjustLogo,
  ArupLogo,
  DoughLogo,
  SourceLogo,
  VahanaLogo,
  ProteoLogo
])
const timer = ref(null)
const currentIndex = ref<number>(0)
const currentImg = computed(() => {
  return images.value[Math.abs(currentIndex.value) % images.value.length];
})

const startSlide = (): void => {
  timer.value = setInterval(next(), 4000);
}

const next = () => {
  currentIndex.value += 1
}
const prev = () => {
  currentIndex.value -= 1
}

</script>

<style scoped lang="scss">
.fade-enter-active,
.fade-leave-active {
  transition: all 0.9s ease;
  overflow: hidden;
  visibility: visible;
  opacity: 1;
}
.fade-enter,
.fade-leave-to {
  visibility: hidden;
  width:100%;
  opacity: 0;
}
img {
  height:600px;
  width:100%
}
.prev, .next {
  cursor: pointer;
  position: absolute;
  top: 40%;
  width: auto;
  padding: 16px;
  color: white;
  font-weight: bold;
  font-size: 18px;
  transition: 0.7s ease;
  border-radius: 0 4px 4px 0;
  text-decoration: none;
  user-select: none;
}
.next {
  right: 0;
}
.prev {
  left: 0;
}
.prev:hover, .next:hover {
  background-color: rgba(0,0,0,0.9);
}
//@import url('https://fonts.googleapis.com/css?family=Roboto+Slab');
//
//.heading {
//  background: white;
//  height: 5%;
//  margin: 10px;
//  padding: 10px;
//}
//
//.swiper-container {
//  width: 100%;
//  height: 90%;
//}
//.swiper-slide {
//  text-align: center;
//  background: #fff;
//  /* Center slide text vertically */
//  display: flex;
//  justify-content: center;
//  align-items: center;
//}
//
//// Image Accordions General
//.container-general {
//  width: 100%;
//  .gallery-wrap {
//    display: flex;
//    flex-direction: row;
//    width: 100%;
//    height: 70vh;
//    .item {
//      flex: 1;
//      height: 500px;
//      width: 100px;
//      background-position: center;
//      background-size: cover;
//      background-repeat: none;
//      transition: all 0.8s ease;
//      &:hover {
//        flex: 7;
//      }
//    }
//  }
//}
</style>