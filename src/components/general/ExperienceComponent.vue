<template>
    <div class="container">
        <div class="titleContainer">
            <img v-if="color == 'red'" :src="ExpIconWhite" alt="icon">
            <img v-else :src="ExpIconRed" alt="icon">
            <h2 class="workPlace title" :class="color == 'red' ? 'redTitle' : 'whiteTitle' ">{{data.title}}</h2>
        </div>
        <h3 class="company title">{{data.company}}</h3>
        <ul>
            <div v-for="exp in data.description" :key="exp" class="listContainer">
                <img :src="color == 'red' ?  WhiteStar : RedStar " alt="icon">
                <p class="text" :class="color == 'red' ? 'redList' : 'whiteList' ">{{exp}}</p>
            </div>
        </ul>
        <p class="title date" :style="color == 'red' ? 'color:#FB9C9C' : 'color:#9E9E9E' ">{{data.date}}</p>
    </div>
</template>
<script setup>
import ExpIconWhite from '@/assets/icons/expIconWhite.svg'
import ExpIconRed from '@/assets/icons/expIconRed.svg'
import WhiteStar from '@/assets/icons/whiteStar.svg'
import RedStar from '@/assets/icons/redStar.svg'

const props = defineProps({
    color:{
        type:String,
        required: false,
        default: 'white'
    },
    data:{
        required: true,
        type: Object
    }
});
</script>
<style scoped>
.titleContainer{
    display: flex;
    gap: 30px;
    align-items: center;
}
.container{
    border-radius: 20px;
    width: 500px;
    padding: 35px 50px;   
    padding-bottom: 1px; 
}

.workPlace{
    margin: 0;
    font-size: 35px;
}

.company{
    margin: 0;
    margin-left: 80px;
    font-size: 30px;
}

ul{
    margin-top: 40px;
    margin-left: 5px;
}

.listContainer{
    display: flex;
    gap: 15px;
    font-size: 20px;
    transition: all 0.3s ease-out;
}

.listContainer:hover{
    transform: translateX(50px);
}

img{
    transition: all 0.3s ease-out;
}

.listContainer:hover > img{
    transform: rotate(360deg);
}

p{
    font-weight: bold;
}

.redTitle{
    color: white;
}

.whiteTitle{
    color: #d24b4b;
}

.redList{
    color: #d0c0c0;
}

.whiteList{
    color: #d24b4b;
}

.date{
    text-align: end;
    margin-right: -10px;
    font-size: 20px;
}
</style>