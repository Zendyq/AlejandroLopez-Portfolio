<template>
    <div class="main">
        <Presentation/>
        <About/>
        <Projects/>
        <Skills/>
        <Experience/>
        <Contact/>
    </div>
</template>
<script setup>
import About from '@/components/home/About.vue';
import Contact from '@/components/home/Contact.vue';
import Experience from '@/components/home/Experience.vue';
import Presentation from '@/components/home/Presentation.vue';
import Projects from '@/components/home/Projects.vue';
import Skills from '@/components/home/Skills.vue';

</script>
<style scoped>
.main{
    display: flex;
    flex-direction: column;
    gap: 250px;    
}
</style>