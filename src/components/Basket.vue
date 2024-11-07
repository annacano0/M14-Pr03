<script setup>
import {ref} from 'vue'

const order=ref([])
</script>

<template>
  <p v-for="(product, index) in order" :key="index" :product="product">{{ orderElement }}</p>
</template>

<style scoped>
</style>
