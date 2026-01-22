<template>
    <div class="mainContainer noselect experienceContainer">
        <h1 class="titleHome title experienceTitle">EXPERIENCE</h1>
        <div class="experiences">
            <ExperienceComponent v-for="(exp,index) in experiences" :key="exp" :data="exp" :class="colorClass(index)" :color="colorClass(index)" />
        </div>
    </div>
</template>
<script setup>
import ExperienceComponent from '../general/ExperienceComponent.vue';
import { experiences } from '@/data/experience';
function colorClass(index) {
  const i = index + 1

  if (i === 1) return 'red'

  return Math.floor((i - 2) / 2) % 2 === 0
    ? 'white'
    : 'red'
}
</script>
<style scoped>
.experienceContainer{
    height: auto;
}

.experienceTitle{
    text-align: center;
}

.experiences{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    width: 80%;
    gap: 100px;
    margin-top: 100px;
}

.red{
    background: #d24b4b;
}

.white{
    background: #d9d9d9;
}
</style>