<template>
  <div class="text-center p-10">
    <div class="w-20 h-20 mx-auto rounded-full bg-[#79a032]">
      <img class="w-20 h-20 rounded-full" src="/images/lufa-logo.png" alt="lufa logo">
    </div>
    <h1 class="text-[#79a032] text-4xl font-bold py-10" >{{ title }}</h1>
    <p class="py-4">{{ text }}</p>
    <p class="py-4">{{ description }}</p>
  </div>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
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
  }
});
</script>
