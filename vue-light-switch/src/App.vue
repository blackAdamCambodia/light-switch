<script setup>
import {ref,reactive} from 'vue';
const onIcon= '//img.icons8.com/?size=512&id=12244&format=png';
const offIcon= '//img.icons8.com/?size=512&id=75&format=png';
const lights = reactive([
  {
    status:0,
    offIcon:offIcon,
    onIcon:onIcon,
    name:'Light 1'
  },
  {
    status:1,
    offIcon:offIcon,
    onIcon:onIcon,
    name:'Light 2'
  },
  {
    status:0,
    offIcon:offIcon,
    onIcon:onIcon,
    name:'Light 3'
  }
]) 
const  bgBlue= 'bg-gray-500';
const  bgGray= 'bg-green-500';
</script>

<template>
  <section class="container mx-auto flex items-center flex-col">
        <h1 class="text-center text-2xl py-10">Assignment</h1>
        <p class="p-5">Click the button and turn on the light</p>
        <div class="flex justify-between space-x-6">
            <div class="p-10 border w-96 flex flex-col space-y-5">
                <button 
                @click="light.status = !light.status"
                 class=" hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
                v-for="(light,index) in lights" :key="index"
                :class="light.status? bgGray : bgBlue ">
                   {{light.name}} {{ light.status? 'ON' : 'OFF' }}
                </button>
                
            </div>
            <div class="p-10 border w-96 flex flex-col space-y-5">
                <img class="w-20" 
                v-for ="light in lights"
                :key="light.name"
                :src="light.status? light.onIcon: light.offIcon" alt="">
              
            </div>
        </div>
    </section>
</template>

<style scoped>

</style>
