<template>
    <div class="slideContainer">
        <div class="video">
            <video :src="WebConysel" 
            autoplay
            muted
            loop
            playsinline>
            </video>
        </div>
        <div class="content">
            <h1 class="title titleContent">WEBS Conysel</h1>
            <hr class="divider">
            <p class="text">Development of a landpage  made with Vue 3 and a CMS built with Strapi</p>
            <div class="techs">
                <img width="75px" v-for="tech in techsSvg" :key="tech" :src="tech" alt="Technologies">
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
import WebConysel from '@/assets/videos/WebConysel.mp4'

const techsSvg = [TailwindSVG, VueSVG, QuasarSVG, JavaScriptSVG, FlutterSVG];

</script>
<style scoped>
.slideContainer{
    width: 100%;
    height: 500px;
    background: #d24b4b;
    border-radius: 20px;
    padding: 35px;
    display: flex;
    gap: 5%;
}

.video {
  flex: 2;
  border-radius: 20px;
  overflow: hidden;
  background: black;
}

.video video {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.2s ease;
}

.video:hover video {
  transform: scale(1.205);
}


.content{
    flex: 3;
    display: flex;
    flex-direction: column;
}

.titleContent{
    color: white;
    font-size: 4rem;
    text-align: center;
    margin: 0;
}

.divider{
    background: black;
    width: 100%;
    height: 7px;
    border-radius: 20px;
    border: none;
}

p{
    color: white;
}

.techs{
    background: #aaaaaa;
    width: 100%;
    height: 100px;
    padding-top: 5px;
    padding-bottom: 5px;
    border-radius: 20px;
    display: flex;
    justify-content: space-around;
    margin-top: auto;
}
</style>