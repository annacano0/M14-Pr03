<script setup>
import MenuItem from './MenuItem.vue'

const products = [
  { name: "Hamburger 🍔", price: 5 },
  { name: "Cheeseburger 🧀", price: 6 },
  { name: "Impossible Burger 🥕", price: 7 },
  { name: "Fries 🍟", price: 2 }
];

</script>

<template>
<div class="menu-container">
  <MenuItem  v-for="(product, index) in products" :key="index" :product="product"></MenuItem>
</div>  
</template>

<style scoped>
.menu-container{
  display: flex;
}
</style>
