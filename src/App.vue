<script setup>
import {
  reactive,
  ref,
} from 'vue';

const images = reactive ([
  {
    lightOnOff: true
  },
  {
    lightOnOff: true
  },
  {
    lightOnOff: true
  },
])

const onLight = "//img.icons8.com/?size=512&id=12244&format=png"
const offLight = "https://img.icons8.com/?size=512&id=75&format=png"
const message = ref("Make These Buttons Work")

const lightControl = (index) => {
  images[index].lightOnOff = !images[index].lightOnOff
  message.value = images[index].lightOnOff ? `Light ${index + 1} is On` : `Light ${index + 1} is Off`
}

</script>

<template>
  <section class="container mx-auto flex items-center flex-col">
        <h1 class="text-center text-2xl py-10">Assignment</h1>
        <p class="p-5"> {{ message }} </p>
        <div class="flex justify-between space-x-6">
            <div class="p-10 border w-96 flex flex-col space-y-5">
                <button @click="lightControl(0)" :class="images[0].lightOnOff ? 'bg-blue-500' : 'bg-gray-500'" class="text-white font-bold py-2 px-4 rounded">
                    {{ images[0].lightOnOff ? 'Light 1 On' : 'Light 1 Off' }}
                </button>
                <button @click="lightControl(1)" :class="images[1].lightOnOff ? 'bg-blue-500' : 'bg-gray-500' " class="text-white font-bold py-2 px-4 rounded">
                    {{ images[1].lightOnOff ? 'Light 2 On' : 'Light 2 Off' }}
                </button>
                <button @click="lightControl(2)" :class="images[2].lightOnOff ? 'bg-gray-500' : 'bg-blue-500'" class="text-white font-bold  py-2 px-4 rounded">
                  {{ images[2].lightOnOff ? 'Light 2 Off' : 'Light 2 On' }}
                </button>
            </div>
            <div class="p-10 border w-96 flex flex-col space-y-5">
                <img class="w-20" :src="images[0].lightOnOff?onLight:offLight" alt="">
                <img class="w-20" :src="images[1].lightOnOff?onLight:offLight" alt="">
                <img class="w-20" :src="images[2].lightOnOff?offLight:onLight" alt="">
            </div>
        </div>
        </section>
</template>
<style scoped>

</style>
