<template>
  <div class="mainContainer noselect">
    <div class="homeSchedule">
      <div class="profileContainer">
        <div class="profileImgWrapper">
          <img class="profileImg" src="@/assets/imgs/FrontSidePicture.svg" alt="Picture of the client">
        </div>
      </div>

      <div>
        <h1 class="titleHome title">Alejandro López Gasco Fernández</h1>
        <p class="subtitleHome title">Full-stack developer</p>
        <div class="skillsHome">
          <img v-for="tech in techsSvg" :key="tech" :src="tech" alt="Technologies">
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import FlutterSVG from '@/assets/imgs/Flutter.svg';
import JavaScriptSVG from '@/assets/imgs/JavaScript.svg';
import QuasarSVG from '@/assets/imgs/Quasar.svg';
import TailwindSVG from '@/assets/imgs/Tailwind.svg';
import VueSVG from '@/assets/imgs/Vue.svg';

const techsSvg = [TailwindSVG, VueSVG, QuasarSVG, JavaScriptSVG, FlutterSVG];

</script>