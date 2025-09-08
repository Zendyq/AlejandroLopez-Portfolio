<template>
    <div class="mainHeader">
        <img class="logo" src="../../assets/imgs/logo.svg" alt="logo">
        <nav class="navBar">
            <router-link class="title weight-700 link" :to="route.path" v-for="route in routes" :key="route">{{ route.name }}</router-link>
        </nav>
    </div>
</template>
<script setup>
import routes from '../../router/routes'
</script>