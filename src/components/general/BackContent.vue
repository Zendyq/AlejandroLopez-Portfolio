<template>
    <div class="backContent">
        <h2 class="titleHome title backTitle">BACK</h2>
        <img class="backImages svg1" :src="BackSvg1" alt="back svg 1">
        <img class="backImages svg2" :src="BackSvg2" alt="back svg 2">
        <img class="backImages svg3" :src="BackSvg3" alt="back svg 3">
        <img class="backImages svg4" :src="BackSvg4" alt="back svg 4">
        <div class="content">
            <div class="webContent">
                <div class="header">
                    <img :src="WebIcon" alt="web icon">
                    <h3 class="miniTitle">Web</h3>
                </div>
                <SkillLine/>
                <div class="skills">
                    <Skill v-for="skill in data.web" :key="skill" :data="skill"/>
                </div>
            </div>
            <div class="desktopContent">
                <div class="header">
                    <img :src="DesktopIcon" alt="web icon">
                    <h3 class="miniTitle">Desktop</h3>
                </div>
                <SkillLine/>
                <div class="skills">
                    <Skill v-for="skill in data.desktop" :key="skill" :data="skill"/>
                </div>
            </div>
            <div class="desktopContent">
                <div class="header">
                    <img :src="desktopIcon" alt="web icon">
                    <h3 class="miniTitle">Mobile</h3>
                </div>
                <SkillLine/>
                <div class="skills">
                    <Skill v-for="skill in data.mobile" :key="skill" :data="skill"/>
                </div>
            </div>
        </div>
    </div>
</template>
<script setup>
import WebIcon from '@/assets/icons/webIcon.svg'
import DesktopIcon from '@/assets/icons/desktopIcon.svg'
import desktopIcon from '@/assets/icons/mobileIcon.svg'
import BackSvg1 from '@/assets/imgs/BackSVG1.svg'
import BackSvg2 from '@/assets/imgs/BackSVG2.svg'
import BackSvg3 from '@/assets/imgs/BackSVG3.svg'
import BackSvg4 from '@/assets/imgs/BackSVG4.svg'
import SkillLine from './SkillLine.vue';
import Skill from './Skill.vue';

const props = defineProps({
    data:{
        type: Object,
        required: true
    }
});
</script>
<style scoped>
.backContent{
    position: relative;
    background: #d9d9d9;
    width: 650px;
    border-radius: 20px;
    padding: 40px 60px;
}

.backTitle{
    font-size: 125px;
    width: 100%;
    text-align: center;
    margin: 0;
    color: #2a2a2a;
}

.webContent{
    margin-top: 55px;
}

.header{
    display: flex;
    gap: 10px;
    padding-left: 15px;
}

.miniTitle{
    font-family: 'DM Sans', sans-serif;
    font-optical-sizing: auto;
    font-style: normal;
    font-size: xx-large;
    margin: 0;
    color: #2a2a2a;
}

.skills{
    display: flex;
    flex-wrap: wrap;
    gap: 9px;
    margin-top: -15px;
}

.desktopContent{
    margin-top: 25px ;
}

.content{
    margin-top: -25px;
}

.backImages{
    position: absolute;
}

.svg1{
    top: 140px;
    left: 50px;
}

.svg2{
    top: 40px;
    left: 100px;
}

.svg3{
    top: 40px;
    right: 100px;
}

.svg4{
    top: 160px;
    right: 50px;
}
</style>