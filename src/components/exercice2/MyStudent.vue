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
    <ul>
      <li v-for="(score, index) in student.scores" :key="index">{{ score }}</li>
    </ul>
  </ul>
</template>

<style scoped></style>
