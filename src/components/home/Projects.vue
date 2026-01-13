<template>
    <div class="mainContainer noselect projectsContainer">
        <h1 class="titleHome title projectsTitle">PROJECTS</h1>
        <Carrousel/>
    </div>
</template>
<script setup>
import Carrousel from '../general/Carrousel.vue';

</script>
<style scoped>
.projectsContainer {
 padding-top:0 ;   
}
.projectsTitle{
    text-align: center;
}
</style>