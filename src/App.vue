<script setup>
import { reactive, ref } from "vue";

const images = reactive({
  lighton1: "//img.icons8.com/?size=512&id=12244&format=png",
  lighton2: "//img.icons8.com/?size=512&id=12244&format=png",
  lightoff: "//img.icons8.com/?size=512&id=75&format=png",
});

const isLightOn1 = ref(true);
const isLightOn2 = ref(true);
const isLightOff = ref(false);

function lightAction(light) {
  if (light === "lighton1") {
    isLightOn1.value = !isLightOn1.value;
    images.lighton1 = isLightOn1.value
      ? "//img.icons8.com/?size=512&id=12244&format=png"
      : "//img.icons8.com/?size=512&id=75&format=png";
  } else if (light === "lighton2") {
    isLightOn2.value = !isLightOn2.value;
    images.lighton2 = isLightOn2.value
      ? "//img.icons8.com/?size=512&id=12244&format=png"
      : "//img.icons8.com/?size=512&id=75&format=png";
  } else if (light === "lightoff") {
    isLightOff.value = !isLightOff.value;
    images.lightoff = isLightOff.value
      ? "//img.icons8.com/?size=512&id=12244&format=png"
      : "//img.icons8.com/?size=512&id=75&format=png";
  }
}
</script>


<template>
  <section class="container mx-auto flex items-center flex-col">
    <h1 class="text-center text-2xl py-10">Assignment</h1>
    <p class="p-5">Make These Buttons Work</p>
    <div class="flex justify-between space-x-6">
      <div class="p-10 border w-96 flex flex-col space-y-5">
        <button
          @click="lightAction('lighton1')"
          class="text-white font-bold py-2 px-4 rounded"
          :class="{ 'bg-blue-500 hover:bg-blue-700': isLightOn1, 'bg-gray-500 hover:bg-gray-700': !isLightOn1 }"
        >
          {{ isLightOn1 ? 'Light 1 On' : 'Light 1 Off' }}
        </button>
        <button
          @click="lightAction('lighton2')"
          class="text-white font-bold py-2 px-4 rounded"
          :class="{ 'bg-blue-500 hover:bg-blue-700': isLightOn2, 'bg-gray-500 hover:bg-gray-700': !isLightOn2 }"
        >
          {{ isLightOn2 ? 'Light 2 On' : 'Light 2 Off' }}
        </button>
        <button
          @click="lightAction('lightoff')"
          class="text-white font-bold py-2 px-4 rounded"
          :class="{ 'bg-gray-500 hover:bg-gray-700': !isLightOff,'bg-blue-500 hover:bg-blue-700': isLightOff }"
        >
          Light 3 Off
        </button>
      </div>
      <div class="p-10 border w-96 flex flex-col space-y-5">
        <img class="w-20" :src="images.lighton1" alt="" />
        <img class="w-20" :src="images.lighton2" alt="" />
        <img class="w-20" :src="images.lightoff" alt="" />
      </div>
    </div>
  </section>
</template>
