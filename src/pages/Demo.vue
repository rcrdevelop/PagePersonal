<template>
  <div>
    <div class="row justify-center text-h3  text-white q-mb-xl fit">
            DEMOS
        </div>

  <div class="animation-page  flex justify-center q-mb-xl">
      <div  @Click="dialog = true; label = item.label; link = item.link" v-for="item in list" :key="item.label" class="q-mb-xl q-ma-sm row demo-container shadow-2 rounded-borders">
          <div class="shineAnimation text-uppercase rounded-borders row items-center justify-center fit">
            {{ item.label }}
          </div>
      </div>
       <q-dialog
      v-model="dialog"
      persistent
      :maximized="maximizedToggle"
      transition-show="slide-up"
      transition-hide="slide-down"
    >
      <q-card class="bg-primary text-white">
        <q-bar>
          <q-space />

          <q-btn dense flat icon="minimize" @click="maximizedToggle = false" :disable="!maximizedToggle">
            <q-tooltip v-if="maximizedToggle" class="bg-white text-primary">Minimize</q-tooltip>
          </q-btn>
          <q-btn dense flat icon="crop_square" @click="maximizedToggle = true" :disable="maximizedToggle">
            <q-tooltip v-if="!maximizedToggle" class="bg-white text-primary">Maximize</q-tooltip>
          </q-btn>
          <q-btn dense flat icon="close" v-close-popup>
            <q-tooltip class="bg-white text-primary">Close</q-tooltip>
          </q-btn>
        </q-bar>

        <q-card-section>
          <div class="text-h6"> {{ label }} </div>
        </q-card-section>

        <q-card-section class="q-pt-none row justify-center bg-white fit ">
            <iframe  class="shadow-2  rounded-borders q-mt-xl" :src="link" frameborder="0"></iframe>
        </q-card-section>
      </q-card>
    </q-dialog>
  </div>
  </div>
</template>
<style>
@media screen and (max-width:600px) {
    .demo-container{
    width: 100%;
    height: 30vh;
    font-size: 1rem;
    }
    iframe{
      width:110%;
      height: 80%;
    }
}
@media screen and (min-width:600px) and (max-width:900px) {
    .demo-container{
        margin-left: 3vw;
        margin-right: 3vw;
        font-size: 1.5rem;
        width: 40%;
        height: 30vh;
    }
    iframe{
      width:50%;
      height: 70%;
    }
}
@media screen and (min-width:900px) {
    .demo-container{
        margin-left: 1vw;
        margin-right: 1vw;
        font-size: 1.5rem;
        width: 40%;
        height: 30vh;
    }
     iframe{
      width:30%;
      height: 90%;
    }
}
.demo-container{
    color: grey;
    background: white;
}
.demo-container:hover{
	background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
	background-size: 400% 400%;
	animation: demo-animation 4s ease infinite;
	-webkit-animation: demo-animation 4s ease infinite;
   color: white;
}
.demo-container:focus{
	background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
	background-size: 400% 400%;
	animation: demo-animation 4s ease infinite;
	-webkit-animation: demo-animation 4s ease infinite;
   color: white;
}
@keyframes demo-animation {
   0% {
		background-position: 0% 50%;
	}

	50% {
		background-position: 100% 50%;

	}

	100% {
		background-position: 0% 50%;
     	}
}
</style>
<script>
import { ref } from 'vue'

export default {
data(){
    return{
        dialog: ref(false),
      maximizedToggle: ref(true),
      label: ref(null),
      link: ref(null),
        list: [
            {
                label:'Build Draw',
                img: '',
                link: 'https://rcrdesarrolloweb.github.io/app-build-draw/#/'
            },
            {
                label:'Game memory',
                img: '',
                link: 'https://rcrdesarrolloweb.github.io/memory-game/'
            },
            {
                label:'Avatar',
                img: '',
                link:'https://rcrdesarrolloweb.github.io/avatar/'
            },
            {
                label:'Shop Online',
                img: '',
                link: 'https://rcrdesarrolloweb.github.io/avak/'
            }
        ]
    }
}
}
</script>

<style>

</style>