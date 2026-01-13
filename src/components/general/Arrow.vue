<template>
    <div class="arrowsContainer" :class="orientation != 'Left' ? 'arrowsLeft' : ''">
        <img :src="BlackArrow" class="BlackArrow" alt="black arrow">
        <img :src="RedArrow" class="RedArrow" alt="red arrow">
        <img :src="WhiteArrow" class="WhiteArrow" alt="white arrow">
    </div>
</template>
<script setup>
import BlackArrow from '@/assets/imgs/BlackArrow.svg'
import RedArrow from '@/assets/imgs/RedArrow.svg'
import WhiteArrow from '@/assets/imgs/WhiteArrow.svg'

const props = defineProps({
    orientation:{
        type: String,
        default: 'Left'
    }
});
</script>
<style scoped>
.arrowsContainer{
    display: inline-flex;
    object-fit: contain;
    cursor: pointer;
}

.arrowsLeft{
    transform: rotate(180deg);
}

.BlackArrow{
    z-index: 4;
    transition: all 0.2s ease-out;
}

.RedArrow{
    z-index: 3;
    margin-left: -80px;
    transition: all 0.2s ease-out;
}

.WhiteArrow{
    z-index: 2;
    margin-left: -80px;
    transition: all 0.2s ease-out;
}

.arrowsContainer:hover .BlackArrow{
    transform: translateX(-40px);
}

.arrowsContainer:hover .WhiteArrow{
    transform: translateX(40px);
}
</style>