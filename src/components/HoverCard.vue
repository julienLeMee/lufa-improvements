<template>
  <div>
    <h1>{{ title }}</h1>
    <p>{{ text }}</p>
    <p>{{ description }}</p>
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
