<template>
  <div class="text-center p-10">
    <!-- <div class="w-[80%] max-h-[80px] mx-auto">
      <img class="object-cover w-full rotate-90 rounded-xl" :src="img" alt="lufa logo">
    </div> -->
    <h1 class="text-[#79a032] text-4xl font-bold py-6" >{{ title }}</h1>
    <p class="py-4 font-bold">{{ text }}</p>
    <p class="py-4">{{ description }}</p>
    <p class="py-4 font-bold uppercase text-xs">{{ text2 }}</p>
  </div>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  // img: {
  //   type: String,
  //   required: true
  // },
  title: {
    type: String,
    required: true
  },
  text: {
    type: String,
    required: true
  },
  description: {
    type: String,
    required: true
  },
  text2 : {
    type: String
  }
});
</script>
