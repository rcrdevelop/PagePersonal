<template>
    <div class="title q-ml-lg q-pa-md text-white text-uppercase">
        front
        <br />end
        <br />developer
    </div>
    <div class="shineAnimation subtitle text-center text-uppercase">vuejs developer</div>
</template>
<style scoped>
@media screen and (max-width: 800px) and (max-height: 1024px) {
    .title {
        top: 15vh;
        font-size: 15vw;
    }
    .subtitle {
        top: 18vh;
        font-size: 5vw;
    }
}
@media screen and (min-width: 800px) and (max-height: 1024px) {
    .title {
        top: 43vh;
        font-size: 15vw;
    }
    .subtitle {
        top: 48vh;
        font-size: 5vw;
    }
}
@media screen and (min-height: 600px) and (min-width: 900px) {
    .title {
        top: 8vh;
        font-size: 8vw;
        margin-left: 10vw;
    }
    .subtitle {
        top: 10vh;
        font-size: 1.5vw;
    }
}
.title {
    position: relative;
    font-weight: 500;
    justify-content: left;
    animation: animation-slide-left 2s linear;
}
.subtitle {
    position: relative;
    font-weight: 400;

    text-align: center;
    
}

.shineAnimation{
background: linear-gradient(
        to right,
         #e73c7e 20%,
        #23a6d5 40%,
        #e73c7e 60%,
        hsl(196, 72%, 49%) 70%,
        #fff 80%
    );
    background-size: 200% auto;

    color: #000;
    background-clip: text;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;

    animation:animation-slide-bottom 8s linear, shine 5s linear infinite; 
}
@keyframes shine {
    to {
        background-position: 200% center;
    }
}
@keyframes animation-slide-left {
    from{
        left: -50%;
        opacity: 0;
    }
    to {
        left: 0%;
        opacity: 1;
    }
}
@keyframes animation-slide-bottom {
    from{
        opacity: 0;
    }
    to {
        opacity: 1;
    }
}


</style>