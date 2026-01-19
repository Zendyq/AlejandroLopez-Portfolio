<template>
  <div class="container" @click="openLink" :data-tooltip="data.name">
    <img :src="data.img" alt="svg">
  </div>
</template>

<script setup>
const props = defineProps({
    data: {
        required: true,
        type: Object
    }
});


function openLink (){
    window.open('https://vuejs.org/');
}
</script>
<style scoped>
.container {
  position: relative;
  background: rgba(170, 170, 170, 0.5);
  border-radius: 20px;
  width: 60px;
  height: 60px;
  padding: 5px;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
}

.container::before {
  content: attr(data-tooltip);
  position: absolute;
  bottom: -42px;
  left: 50%;
  transform: translateX(-50%) translateY(6px) scale(0.95);
  background: #424242;
  color: #fff;
  font-family: 'DM Sans', sans-serif;
  font-size: 12px;
  padding: 4px 10px;
  border-radius: 12px;
  white-space: nowrap;
  opacity: 0;
  pointer-events: none;
  transition:
    opacity 0.2s ease,
    transform 0.2s ease;
  z-index: 10;
}

.container::after {
  content: '';
  position: absolute;
  bottom: -20px;
  left: 50%;
  transform: translateX(-50%) translateY(6px);
  border: 6px solid transparent;
  border-top: none;
  border-bottom: 6px solid #424242;
  opacity: 0;
  pointer-events: none;
  transition:
    opacity 0.2s ease,
    transform 0.2s ease;
  z-index: 9;
}

.container:hover::before,
.container:hover::after {
  opacity: 1;
  transform: translateX(-50%) translateY(-10px) scale(1);
}

img {
  width: 80%;
}


</style>