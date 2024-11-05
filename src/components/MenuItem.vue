<script setup>
import { defineProps, computed, inject } from 'vue'

const props = defineProps({
  product: Object
})

const currency = inject('currency')

const calculatedPrice = computed(() => {
  if (currency === 'euro') {
    return (props.product.price * 0.85).toFixed(2) 
  }
  return props.product.price.toFixed(2) 
})

const addToCart=()=>{
  console.log("add product")
}
</script>

<template>
  <div class="product-container">
    <p>{{ props.product.name }}</p>
    <p>{{ calculatedPrice }}{{ currency === 'euro' ? '€' : '$' }}</p>
    <button @click="addToCart">Add to cart</button>
  </div>
</template>

<style scoped>
.product-container{
  background-color: rgb(146, 166, 255);
  width: 12em;
  border-radius: 1em;
  padding: 0.5em;
  display: flex;
  flex-direction: column;
  margin: 0.5em;
}

.product-container{
  text-align: center;
}
</style>
