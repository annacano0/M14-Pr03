<script setup>
import { ref, provide } from 'vue'
import MenuList from './MenuList.vue'

const title = ref('This is the title')

const placeOrder = () => {
  console.log("click en place order")
}

const currency = ref('')
provide('currency', currency)
</script>

<template>
  <header>
      <h1>{{ title ? title : 'New Order' }}</h1>
      <input type="text" v-model="title" placeholder="Write a new name here">
      <button @click="placeOrder">Place Order</button>
  </header>
  <div class="currency-container">
    <p>Currency</p>
    <select v-model="currency">
      <option value="euros">Euros (€)</option>
      <option value="dollars">Dollars ($)</option>
    </select>
  </div>
  <MenuList/>
</template>

<style scoped>
</style>
