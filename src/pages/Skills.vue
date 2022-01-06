<template>
    <div class=" bg-transparent justify-center row items-center">
        <div class="row justify-center text-h3  text-white q-mb-xl fit">
            SKIILS
        </div>
        <div class="animation-page shadow-15 rounded-borders container bg-white row items-center justify-around q-pa-lg ">
            <div v-for="item in list" :key="item.label">
                <div :class="'brand-container q-pa-md q-ma-sm row justify-center items-center '+item.extra" 
                    >
                    <q-icon
                        :class="'brand '+item.color"
                        :key="item.img"
                        :name="item.img"
                    />
                   
                </div>
                 <div class="text-brand text-center text-grey text-bold">
                        {{ item.label }}
                    </div>
                </div>
            </div>
        </div>
</template>
<style>
@media screen and (max-width: 600px) {
    .text-brand{
        font-size: 4vw;
    }
    .brand-container{

        width: 20vw;
        height: 20vw;
         border-radius: 50% 50%;
    }
    .brand{
        font-size: 10vw;
    }
    .container{
        height: 70vh;
    }
}
@media screen and (min-width: 600px) and (max-width: 900px) {
    .text-brand{
        font-size: 2.5vw;
    }
    .brand-container{
        margin: 2vw;
        width: 15vw;
        height: 15vw;
        border-radius: 50% 50%;
    }
    .brand{
        font-size: 8vw;
    }
}

@media screen and (min-width: 900px) {
    .text-brand{
        font-size: 1.5vw;
    }
    .container{
        height: 50vh;
    }
    .brand-container{
        margin: 1vw;
        width: 10vw;
        height: 10vw;
        border-radius: 50% 50%;
    }
    .brand{
        font-size:5vw;
    }
}

</style>
<script>
    export default{
        data(){
            return{
                list:[
                    {
                        label: 'vuejs3',
                        img: 'lab la-vuejs',
                        color: 'text-green-14',
                        extra: 'inset-shadow'
                    },
                    {
                        label: 'git',
                        img: 'lab la-git',
                        color: 'text-orange-7',
                        extra: 'inset-shadow-down'
                    },
                    {
                        label: 'serveless',
                        img: 'lab la-aws',
                        color: 'text-orange-10',
                        extra: 'inset-shadow'
                    },
                    {
                        label: 'nosql',
                        img: 'fas fa-database',
                        color: 'text-grey-9',
                        extra: 'inset-shadow-down'
                    },
                    {
                        label: 'ux/ui',
                        img: 'lab la-sketch',
                        color: 'text-yellow-9',
                        extra: 'inset-shadow'
                    },
                    {
                        label: 'nodejs',
                        img: 'lab la-node-js',
                        color: 'text-green',
                        extra: 'inset-shadow-down'
                    }
                ]
            }
        }
    }
</script>