<template>
    <div class="mainContainer noselect contactContainer">
        <h1 class="titleHome title contactTitle">CONTACT</h1>
        <img class="arrows arrow1" :src="Arrow1" alt="arrow 1">
        <img class="arrows arrow2" :src="Arrow2" alt="arrow 2">
        <img class="arrows arrow3" :src="Arrow3" alt="arrow 3">
        <ContactComponent/>
    </div>
</template>
<script setup>
import Arrow1 from '@/assets/imgs/Arrow1.svg'
import Arrow2 from '@/assets/imgs/Arrow2.svg'
import Arrow3 from '@/assets/imgs/Arrow3.svg'
import ContactComponent from '../general/ContactComponent.vue';

</script>
<style scoped>
.contactContainer{
    position: relative;
    padding-bottom: 50px;
}

.arrows{
    position: absolute;
}

.arrow1{
    top: 0;
}

.arrow2{
    top: 0;
}

.arrow3{
    top: 0;
}
.contactTitle{
    text-align: center;
    margin-bottom: 150px;
}
</style>