<template>
    <div class="mainContainer noselect skillsContainer">
        <h1 class="titleHome title skillsTitle">SKILLS</h1>
        <div class="contentContainer">
            <BackContent :data="skills.back"/>
            <FrontContent :data="skills.front"/>
        </div>
    </div>
</template>
<script setup>
import BackContent from '../general/BackContent.vue';
import FrontContent from '../general/FrontContent.vue';
import { skills } from '@/data/skills'


</script>
<style scoped>
.skillsContainer{
    padding-left: 0;
}

.skillsTitle{
    text-align: center;
    width: 100%;
    margin-bottom: 40px;
}

.contentContainer{
    display: flex;
    margin: auto;
    justify-content: center;
    gap: 7%;
}
</style>