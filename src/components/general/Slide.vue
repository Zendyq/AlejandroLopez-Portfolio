<template>
    <div class="slideContainer">
        <div class="video">
            <video :src="data.video" 
            autoplay
            muted
            loop
            playsinline>
            </video>
        </div>
        <div class="content">
            <h1 class="title titleContent"> {{data.title}}</h1>
            <hr class="divider">
            <p class="text">{{data.description}}</p>
            <div class="techs">
                <img width="75px" v-for="tech in data.techs" :key="tech" :src="tech" alt="Technologies">
            </div>
        </div>
    </div>
</template>
<script setup>
const props = defineProps({
    data:{
        required: true,
        type: Object
    }
});

</script>
<style scoped>
.slideContainer{
    width: 100%;
    height: 500px;
    background: #d24b4b;
    border-radius: 20px;
    padding: 35px;
    display: flex;
    gap: 5%;
}

.video {
  flex: 2;
  border-radius: 20px;
  overflow: hidden;
  background: black;
}

.video video {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.2s ease;
}

.video:hover video {
  transform: scale(1.205);
}


.content{
    flex: 3;
    display: flex;
    flex-direction: column;
}

.titleContent{
    color: white;
    font-size: 4rem;
    text-align: center;
    margin: 0;
}

.divider{
    background: black;
    width: 100%;
    height: 7px;
    border-radius: 20px;
    border: none;
}

p{
    color: white;
}

.techs{
    background: #aaaaaa;
    width: 100%;
    height: 100px;
    padding-top: 5px;
    padding-bottom: 5px;
    border-radius: 20px;
    display: flex;
    justify-content: space-around;
    margin-top: auto;
}
</style>