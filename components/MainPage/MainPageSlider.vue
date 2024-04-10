<script setup>
import { register } from "swiper/element/bundle";
import { onMounted } from 'vue'
register();

const slides = [
  '/logos/logo-1.png',
  '/logos/logo-2.png',
  '/logos/logo-3.png',
  '/logos/logo-5.png',
  '/logos/logo-6.png',
  '/logos/logo-4.png',
  '/logos/logo-8.png',
  '/logos/logo-7.png',
]

onMounted(() => {
  const swiperElement = document.querySelector('#main-page__swiper');
  if (swiperElement) {
    const shadowRoot = swiperElement.shadowRoot;
    if (shadowRoot) {
      const style = document.createElement('style');
      style.textContent = `           
        .swiper-wrapper {
          align-items: center;
        }            
      `;
      shadowRoot.appendChild(style);
    }
  }
});
</script>

<template>
    <div class="main-page__swiper">
    <swiper-container 
    slides-per-view="3" 
    autoplay-delay="2200"
    speed="2000" 
    space-between="71" 
    loop="true" 
    :breakpoints="{
      768: {
        slidesPerView: 6,
      },
      1440: {
        slidesPerView: 7,
      },
    }"
    id="main-page__swiper">
      <swiper-slide v-for="(slide, index) in slides" :key="index">
        <div class="advertising__slide"><img class="swiper-logo-img" :src="slide" alt="" /></div>
      </swiper-slide>     
    </swiper-container>
  </div>
</template>
<style lang="scss" scoped>
.main-page__swiper {
    margin-bottom: clamp(80px, 19vw, 150px);
}
</style>