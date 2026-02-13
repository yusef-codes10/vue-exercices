<script setup>
// Exercise 2: Student Grade Calculator
// javascript
// const students = ref([
//   { name: 'Alice', scores: [85, 92, 78, 90] },
//   { name: 'Bob', scores: [70, 65, 80, 75] },
//   { name: 'Charlie', scores: [95, 98, 100, 97] },
//   { name: 'Diana', scores: [60, 55, 58, 62] }
// ])
// Create computed properties for:

// studentsWithAverages - Add an average property to each student
// topStudent - Student with highest average
// passingStudents - Students with average >= 70
// classAverage - Average of all students' averages
// gradeDistribution - Count of A's, B's, C's, D's, F's (A: 90+, B: 80-89, etc.)

import { ref } from 'vue'

const students = ref([
  { name: 'Alice', scores: [85, 92, 78, 90] },
  { name: 'Bob', scores: [70, 65, 80, 75] },
  { name: 'Charlie', scores: [95, 98, 100, 97] },
  { name: 'Diana', scores: [60, 55, 58, 62] },
])
</script>

<template>
  <div class="student">
    <ul v-for="student in students" :key="student.name">
      <li>Name: {{ student.name }}</li>
      <ul>
        Grades:
        <li v-for="(grade, index) in student.scores" :key="index">{{ grade }}</li>
      </ul>
    </ul>
  </div>
</template>

<style scoped></style>
