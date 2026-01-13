<template>
  <div class="mainContainer noselect aboutMeContainer">
    <div class="firstContainer">
        <h1 class="titleHome title aboutTitle">ABOUT ME</h1>
        <p class="subtitleHome title aboutSubtitle">Hi! I´m Alex 😉 A frontend web developer passionate about solving creative challenges with responsive, cross-platform tools</p>
        <div class="buttonsContainer">
            <CoolButtons label="Projects" @pressed="console.log('pulsado')"/>
            <CoolButtons label="Experience" style="decorated"/>
        </div>
    </div>
    <div class="secondContainer">
        <img :src="BlackAndWhitePicture" width="50%" alt="black and white picture">
        <p class="subtitleHome title cite">- "Always aiming for the most beautiful result, and always with a smile."</p>
    </div>
  </div>
</template>

<script setup>
import BlackAndWhitePicture from '@/assets/imgs/BlackWhitePicture.svg';
import CoolButtons from '@/components/general/CoolButtons.vue';
</script>

<style scoped>
.aboutMeContainer{
  display: flex;
}

.firstContainer{
  flex: 7;
  max-height: fit-content;
}

.secondContainer{
  flex: 8;
  max-height: fit-content;
}

.aboutTitle{
    text-align: center;
}

.aboutSubtitle{
    width: 75%;
    margin-top: 10%;
}

.cite{
    width: 40%;
    margin-left: 40px;
}

.buttonsContainer{
    display: flex;
    gap: 15%;
    margin-top: 15%;
}
</style>