<script setup>
// Exercice 1
// Exercise 1: E-commerce Cart
// javascript
// const cart = ref([
//   { id: 1, name: 'Laptop', price: 999, quantity: 1, taxRate: 0.15 },
//   { id: 2, name: 'Mouse', price: 25, quantity: 2, taxRate: 0.15 },
//   { id: 3, name: 'Keyboard', price: 75, quantity: 1, taxRate: 0.15 }
// ])
// Create computed properties for:

// subtotal - Sum of (price × quantity) for all items
// tax - Total tax amount
// total - Subtotal + tax
// itemCount - Total number of items in cart
// averageItemPrice - Average price per item

import { ref } from 'vue'

const cart = ref([
  { id: 1, name: 'Laptop', price: 999, quantity: 1, taxRate: 0.15 },
  { id: 2, name: 'Mouse', price: 25, quantity: 2, taxRate: 0.15 },
  { id: 3, name: 'Keyboard', price: 75, quantity: 1, taxRate: 0.15 },
])

console.log(cart.value)
</script>

<template>
  <h1>Exercice 1</h1>
  <h2>Cart:</h2>
  <div class="cart">
    <ul v-for="item in cart" :key="item.id">
      <li>id: {{ item.id }}</li>
      <li>Product: {{ item.name }}</li>
      <li>Price: ${{ item.price }}</li>
      <li>quantity: {{ item.quantity }}</li>
      <li>Tax rate: {{ item.taxRate }}</li>
    </ul>
  </div>
</template>

<style scoped></style>
