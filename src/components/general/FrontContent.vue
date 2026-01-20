<template>
    <div class="frontContent">
        <h2 class="titleHome title frontTitle">FRONT</h2>
        <img class="frontImages svg1" :src="FrontSVG1" alt="Front svg 1">
        <img class="frontImages svg2" :src="FrontSVG2" alt="Front svg 2">
        <img class="frontImages svg3" :src="FrontSVG3" alt="Front svg 3">
        <img class="frontImages svg4" :src="FrontSVG4" alt="Front svg 4">
        <div class="content">
            <div class="webContent">
                <div class="header">
                    <img :src="WebIcon" alt="web icon">
                    <h3 class="miniTitle">Web</h3>
                </div>
                <SkillLine color="white"/>
                <div class="skills">
                    <Skill v-for="skill in data.web" :key="skill" :data="skill"/>
                </div>
            </div>
            <div class="desktopContent">
                <div class="header">
                    <img :src="DesktopIcon" alt="web icon">
                    <h3 class="miniTitle">Desktop</h3>
                </div>
                <SkillLine color="white"/>
                <div class="skills">
                    <Skill v-for="skill in data.desktop" :key="skill" :data="skill"/>
                </div>
            </div>
            <div class="desktopContent">
                <div class="header">
                    <img :src="desktopIcon" alt="web icon">
                    <h3 class="miniTitle">Mobile</h3>
                </div>
                <SkillLine color="white"/>
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
import FrontSVG1 from '@/assets/imgs/FrontSVG1.svg'
import FrontSVG2 from '@/assets/imgs/FrontSVG2.svg'
import FrontSVG3 from '@/assets/imgs/FrontSVG3.svg'
import FrontSVG4 from '@/assets/imgs/FrontSVG4.svg'
import Skill from './Skill.vue'
import SkillLine from './SkillLine.vue'

const props = defineProps({
    data:{
        type: Object,
        required: true
    }
});

</script>
<style scoped>
.frontContent{
    position: relative;
    background: #d24b4b;
    width: 650px;
    border-radius: 20px;
    padding: 40px 60px;
}

.frontTitle{
    font-size: 125px;
    width: 100%;
    text-align: center;
    margin: 0;
}

.content{
    margin-top: -25px;
}
.webContent{
    margin-top: 55px;
}

.desktopContent{
    margin-top: 25px ;
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
    color: white;
}

.skills{
    display: flex;
    flex-wrap: wrap;
    gap: 9px;
    margin-top: -15px;
}

.frontImages{
    position: absolute;
}

.svg1{
    top: 140px;
    left: 80px;
}

.svg2{
    top: 20px;
    left: 40px;
}

.svg3{
    top: 160px;
    right: 120px;
}

.svg4{
    top: 40px;
    right: 40px;
}
</style>