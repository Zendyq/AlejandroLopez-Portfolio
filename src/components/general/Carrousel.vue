<template>
  <div class="carousel">
    <div class="carousel-track">
      <div
        v-for="(slide, index) in projects"
        :key="index"
        class="carousel-slide"
        :class="{
          active: index === currentIndex,
          prev: index === prevIndex,
          next: index === nextIndex
        }"
      >
      <Slide :data="slide"/>
      </div>
    </div>
    <Arrow orientation="Left" class="prevArrow" @click="prev"/>
    <Arrow orientation="Right" class="nextArrow" @click="next"/>
  </div>
</template>
<script setup>
import { ref, computed } from 'vue'
import Slide from './Slide.vue'
import Arrow from './Arrow.vue'
import { projects } from '@/data/projects'


const currentIndex = ref(0)

const next = () => {
  currentIndex.value = (currentIndex.value + 1) % projects.length
}

const prev = () => {
  currentIndex.value = (currentIndex.value - 1 + projects.length) % projects.length
}

const prevIndex = computed(() => (currentIndex.value - 1 + projects.length) % projects.length)
const nextIndex = computed(() => (currentIndex.value + 1) % projects.length)
</script>
<style scoped>
.carousel {
  position: relative;
  width: 80%;
  height: 300px;
  margin: 200px auto 0 auto;
  perspective: 1000px;
  overflow: visible;
}

.carousel-track {
    width: 95.5%;
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

.prevArrow{
    position: absolute;
    top: 50px;
    left: 30px;
    z-index: 10;
}

.nextArrow{
    position: absolute;
    top: 50px;
    right: 30px;
    z-index: 10;
}
</style>
