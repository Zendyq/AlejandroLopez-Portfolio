<template>
    <div class="mainHeader">
        <img class="logo" @click="toHome" src="../../assets/imgs/Logo.svg" alt="Header logo">
        <nav class="navBar">
            <router-link class="title weight-700 link" :to="route.path" v-for="route in routes" :key="route">{{ route.name }}</router-link>
        </nav>
        <button class="burguerBtn" @click="isMenuOpen = !isMenuOpen" aria-label="Abrir menú">
            <img src="@/assets/imgs/NavIcon.svg" class="burguerIcon" alt="Icon navigation menu" />
        </button>
        <nav class="navBarMenu" :class="{open: isMenuOpen}">
            <router-link class="title weight-700 link" :to="route.path" v-for="route in routes" :key="route">{{ route.name }}</router-link>
        </nav>
    </div>
</template>
<script setup>
import { ref } from 'vue';
import routes from '../../router/routes'
import { useRouter } from 'vue-router';

const isMenuOpen = ref(false);
const router = useRouter();

function toHome(){
    router.push({name:'HOME'});
}
</script>