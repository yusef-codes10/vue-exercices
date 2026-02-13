<script setup>
import MyStudent from './MyStudent.vue'

import { ref } from 'vue'

const students = ref([
  {
    name: 'Alice',
    scores: [
      { subject: 'Math', score: 85 },
      { subject: 'Science', score: 92 },
      { subject: 'English', score: 78 },
      { subject: 'History', score: 90 },
    ],
  },
  {
    name: 'Jake',
    scores: [
      { subject: 'Math', score: 70 },
      { subject: 'Science', score: 65 },
      { subject: 'English', score: 80 },
      { subject: 'History', score: 75 },
    ],
  },
  {
    name: 'Charlie',
    scores: [
      { subject: 'Math', score: 95 },
      { subject: 'Science', score: 98 },
      { subject: 'English', score: 100 },
      { subject: 'History', score: 97 },
    ],
  },
  {
    name: 'Diana',
    scores: [
      { subject: 'Math', score: 60 },
      { subject: 'Science', score: 55 },
      { subject: 'English', score: 58 },
      { subject: 'History', score: 62 },
    ],
  },
])

// more students
const name = ref('')
const addStudent = () => {
  if (name.value.trim() !== '') {
    students.value.push({ name: name.value, scores: [] })
  }
  name.value = ''
}
</script>

<template>
  <div class="students">
    <div class="student">
      <MyStudent v-for="student in students" :key="student.name" :student="student" />
    </div>
    <div class="admin">
      <h2>Enter a new Student:</h2>
      <label for="name">Name: </label>
      <input type="text" id="name" v-model="name" />
      <button @click="addStudent">Add Student</button>
    </div>
  </div>
</template>

<style scoped>
.students {
  display: flex;
}

.student {
  width: 50%;
  background-color: seagreen;
}
</style>
