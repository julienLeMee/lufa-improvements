<template>
  <div class="text-center p-8">
    <h1 class="text-[#79a032] text-4xl font-bold pb-4" >{{ title }}</h1>
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
