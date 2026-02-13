<script setup>
import { defineProps } from 'vue'

defineProps({
  student: {
    type: Object,
    required: true,
  },
})
</script>

<template>
  <ul>
    <li>Name {{ student.name }}</li>
    <li v-for="(score, index) in scores" :key="index">{{ score }}</li>
  </ul>
</template>

<style scoped></style>
