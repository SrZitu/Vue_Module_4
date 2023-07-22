<script setup>
import { ref,reactive } from 'vue';
let location=reactive({
  name:"Dhaka",
  wheather:"sunny",

});

function changeLocation(newLocation,newwheather){
location.name=newLocation;
location.wheather=newwheather;

}
</script>

<template>
 <section class="container mx-auto flex items-center flex-col">
        <h1 class="text-center text-2xl py-10">Events & Reactivity in Vue.js</h1>
        <div class="container mx-auto flex space-x-5 justify-center m-5">
            <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" @click="changeLocation('Dhaka','Sunny')">
                Dhaka
            </button>
            <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" @click="changeLocation('Rashahi','Cloudy')">
                Rajshahi
            </button>
              <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" @click="changeLocation('Khulna','Thunder')">
                Khulna
            </button>
            
        </div>
        <h1 class="text-2xl m-10 text-blue-500">Current Location is {{ location.name }} <br/>Wheather:{{ location.wheather }} </h1>
    </section>
</template>

<style scoped></style>