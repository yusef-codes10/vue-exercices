<script setup>
import MyStudent from './MyStudent.vue'

import { ref } from 'vue'

const students = ref([
  { name: 'Alice', scores: [85, 92, 78, 90] },
  { name: 'Jake', scores: [70, 65, 80, 75] },
  { name: 'Charlie', scores: [95, 98, 100, 97] },
  { name: 'Diana', scores: [60, 55, 58, 62] },
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
