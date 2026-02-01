<template>
    <div class="container">
        <div class="copyBtn" @click="copyToClipboard">
            <img class="copyIcon" :src="CopySVG" alt="copy icon">
            <p v-if="showTooltip" class="tooltip">✓ Copiado</p>
        </div>
        <div class="infoImageContainer">
            <img class="infoImage"  :src="data.img" alt="info icon">
        </div>
        <h1 class="title infoTitle">{{data.title}}</h1>
        <p class="title info">{{data.info}}</p>
    </div>
</template>
<script setup>
import LinkEdin from '@/assets/imgs/LinkEdin.svg'
import CopySVG from '@/assets/imgs/Copy.svg'
import { ref } from 'vue';

const props = defineProps({
    data:{
        type: Object,
        required: true
    }
});

const showTooltip = ref(false);

function copyToClipboard() {
    navigator.clipboard.writeText(props.data.link);
    showTooltip.value = true;
    setTimeout(() => {
        showTooltip.value = false;
    }, "1000");}
    
</script>
<style scoped>
.container{
    position: relative;
    width: 25%;
    height: 600px;
    background: #d9d9d9;
    border-radius: 20px;
    box-shadow: -10px 10px 0px #d24b4b;
}

.infoImageContainer{
    padding-top: 90px;
    display: flex;
    align-items: center;
}

.infoImage{
    margin: auto;
    width: 40% ;
}

.infoTitle{
    text-align: center;
    font-size: 100px;
    margin: 0;
    color: #2a2a2a;
    margin-top: 40px;
}

.info{
    color: #2a2a2a;
    text-align: center;
    font-weight: bold;
    font-size: 24px;
    margin-top: 40px;
}

.copyBtn {
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 20px;
  width: 75px;
  height: 75px;
  background: #2a2a2a;
  box-shadow:
    -6px 6px 0px #464646,
    -6px 6px 12px rgba(0, 0, 0, 0.25);
  position: absolute;
  top: 15px;
  right: 15px;
  cursor: pointer;

  transition:
    transform 0.12s ease-out,
    box-shadow 0.12s ease-out,
    background 0.12s ease-out;
}

.copyBtn:hover {
  transform: translate(-2px, 2px);
  background: #333;

  box-shadow:
    -4px 4px 0px #464646,
    -4px 4px 8px rgba(0, 0, 0, 0.25);
}

.copyBtn:active {
  transform: translate(-6px, 6px);
  background: #1f1f1f;

  box-shadow:
    0px 0px 0px #464646,
    0px 0px 4px rgba(0, 0, 0, 0.3);
}

.copyIcon{
    width: 70%;
}

.tooltip{
    position: absolute;
    bottom: -60px;
    right: -10px;
    width: 100px;
    text-align: center;
    background: #d24b4b;
    border-radius: 20px;
    padding: 3px;
    color: #d9d9d9;
    font-weight: bold;
}

</style>