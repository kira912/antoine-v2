<template>
  <div class="swiper-container">
    <div class="swiper-wrapper">
      <div class="swiper-slide">
        <div class="container-general">
          <div class="gallery-wrap wrap-effect-1">
            <img class="item" src="@/assets/ImpactLogo.jpg" />
            <img class="item" src="@/assets/AjustLogo.jpg" />
            <img class="item" src="@/assets/ArupLogo.jpg" />
            <img class="item" src="@/assets/DoughLogo.jpg" />
            <img class="item" src="@/assets/SourceLogo.png" />
            <img class="item" src="@/assets/VahanaLogo.png" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { onMounted, ref } from "vue";
import { Swiper, SwiperSlide } from 'swiper/vue';


</script>

<style scoped lang="scss">
@import url('https://fonts.googleapis.com/css?family=Roboto+Slab');

.heading {
  background: white;
  height: 5%;
  margin: 10px;
  padding: 10px;
}

.swiper-container {
  width: 100%;
  height: 90%;
}
.swiper-slide {
  text-align: center;
  background: #fff;
  /* Center slide text vertically */
  display: flex;
  justify-content: center;
  align-items: center;
}

// Image Accordions General
.container-general {
  width: 100%;
  .gallery-wrap {
    display: flex;
    flex-direction: row;
    width: 100%;
    height: 70vh;
    .item {
      flex: 1;
      height: 500px;
      width: 100px;
      background-position: center;
      background-size: cover;
      background-repeat: none;
      transition: all 0.8s ease;
      &:hover {
        flex: 7;
      }
    }
  }
}
</style>