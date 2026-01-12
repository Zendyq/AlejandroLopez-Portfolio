<template>
    <div class="mainContainerButton" 
    :class="style == 'Minimalist' ? 'minimalist' : 'decorated'" 
    @click="clicked()">
        <p class="subtitleHome title">{{label}}</p>
        <img v-if="style != 'Minimalist'" class="star star1" :src="Star" alt="star 1">
        <img v-if="style != 'Minimalist'" class="star star2" :src="Star" alt="star 2">
        <img v-if="style != 'Minimalist'" class="star star3" :src="Star" alt="star 3">
        <img v-if="style != 'Minimalist'" class="star star4" :src="Star" alt="star 4">
        <img v-if="style != 'Minimalist'" class="star star5" :src="Star" alt="star 5">
    </div>
</template>
<script setup>
import { defineEmits, defineProps } from 'vue';
import Star from '@/assets/imgs/Star.svg'
const props = defineProps({
    style:{
        type: String,
        default: 'Minimalist',
    },
    label:{
        required: true,
        type: String
    }
});

const emit = defineEmits(['pressed']);

function clicked(){
    emit('pressed')
}
</script>
<style scoped>
.mainContainerButton{
    position: relative;
    padding: 40px;
    padding-top: 20px;
    padding-bottom: 20px;
    width: 175px;
    border-radius: 20px;
    margin: 0;
    cursor: pointer;
    overflow: hidden;
}

.minimalist{
    background: black;
}

.decorated{
    background: #f03b3c;
}

p{
    position: relative;
    margin: 0;
    text-align: center;
    z-index: 2;
    transition: all 0.2s ease-out;
}

.mainContainerButton:hover p{
    text-shadow: 3px 3px #f03b3c;
}

.star{
    position: absolute;
    z-index: 1;
    pointer-events: none;
    transition: all 1s ease-out;
}

.star1{
    top: 0;
    width: 15%;
    left: 15px;
}

.star2{
    top: 55px;
    left: 50px;
    width: 10%;
    transform: rotate(90deg);
}

.star3{
    top: 0;
    right: 45px;
    width: 15%;
    transform: rotate(90deg);
}

.star4{
    top: 35px;
    right: 5px;
    width: 15%;
}

.star5{
    top: 0;
    right: 45px;
    width: 15%;
    transform: rotate(90deg);
}

.mainContainerButton:hover .star1{
    transform: rotate(300deg);
    width: 30%;
}

.mainContainerButton:hover .star2{
    transform: rotate(320deg);
    width: 30%;
    top: 0;
}

.mainContainerButton:hover .star3{
    transform: rotate(340deg);
    width: 30%;
    top: 0;
    right: 90px;
}

.mainContainerButton:hover .star4{
    transform: rotate(360deg);
    width: 30%;
    top: 0;
    right: 20px;
}
.mainContainerButton:hover .star5{
    transform: rotate(380deg);
    width: 30%;
    top: 0;
    right: 50px;
}

</style>