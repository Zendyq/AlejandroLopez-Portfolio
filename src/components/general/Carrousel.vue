<template>
  <div class="carousel">
    <div class="carousel-track">
      <div
        v-for="(slide, index) in slides"
        :key="index"
        class="carousel-slide"
        :class="{
          active: index === currentIndex,
          prev: index === prevIndex,
          next: index === nextIndex
        }"
      >
      <Slide/>
        <!--<img :src="slide" alt="slide" />-->
      </div>
    </div>

    <button class="prev" @click="prev">‹</button>
    <button class="next" @click="next">›</button>
  </div>
</template>
<script setup>
import { ref, computed } from 'vue'
import Slide from './Slide.vue'

const slides = [
  'https://picsum.photos/id/1015/400/250',
  'https://picsum.photos/id/1016/400/250',
  'https://picsum.photos/id/1018/400/250',
  'https://picsum.photos/id/1020/400/250',
  
]

const currentIndex = ref(0)

const next = () => {
  currentIndex.value = (currentIndex.value + 1) % slides.length
}

const prev = () => {
  currentIndex.value = (currentIndex.value - 1 + slides.length) % slides.length
}

const prevIndex = computed(() => (currentIndex.value - 1 + slides.length) % slides.length)
const nextIndex = computed(() => (currentIndex.value + 1) % slides.length)
</script>
<style scoped>
.carousel {
  position: relative;
  width: 80%;
  height: 300px;
  margin-top: 200px;
  perspective: 1000px;
  overflow: visible;
}

.carousel-track {
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
  height: 100%;
}

.carousel-slide {
  position: absolute;
  transition: all 0.5s ease;
  width: 70%;
  opacity: 0.3;
  transform: scale(0.8) translateX(0) translateZ(-100px);
  z-index: 1;
  border-radius: 20px;
}

.carousel-slide.active {
  opacity: 1;
  transform: scale(1) translateX(0) translateZ(0);
  z-index: 3;
}

.carousel-slide.prev {
  transform: scale(0.8) translateX(-120%) translateZ(-50px);
  z-index: 2;
}

.carousel-slide.next {
  transform: scale(0.8) translateX(120%) translateZ(-50px);
  z-index: 2;
}

button {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background: rgba(0,0,0,0.5);
  color: white;
  border: none;
  font-size: 2rem;
  cursor: pointer;
  z-index: 4;
}

.prev { left: 10px; }
.next { right: 10px; }
</style>
