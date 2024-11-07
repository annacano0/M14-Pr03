<script setup>
import { defineProps, computed, inject, toRef } from 'vue'

const props = defineProps({
  product: Object
})
const currency = inject('currency')

const calculatedPrice = computed(() => {
  if (currency.value === 'euro') {
    return (props.product.price * 0.85).toFixed(2) 
  }
  return props.product.price.toFixed(2) 
})

const addToCart = () => {
  console.log("add product")
}
</script>

<template>
  <div class="product-container">
    <p>{{ props.product.name }}</p>
    <p>{{ calculatedPrice }}{{ currency === 'euros' ? '€' : '$' }}</p>
    <button @click="addToCart">Add to cart</button>
  </div>
</template>

<style scoped>
.product-container{
  background-color: rgb(255, 146, 188);
  width: 6em;
  border-radius: 1em;
  padding: 0.5em;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  margin: 0.5em;
}

.product-container{
  text-align: center;
}
</style>
