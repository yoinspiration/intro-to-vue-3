<script setup>
import { ref } from 'vue'

const product = ref('Socks')
const description = ref('A pair of warm, fuzzy socks')
const image = ref('./src/assets/images/socks-green.jpg')
const url = ref('https://intro-to-vue-3-tgd7.onrender.com/')
const inventory = ref(0)
const details = ref(['50% cotton', '30% wool', '20% polyester'])
const variants = ref([
  { id: 2234, color: 'green' },
  { id: 2235, color: 'blue' }
])
</script>

<template>
  <h1>{{ product }}</h1>

  <img :src="image" :alt="description" />

  <a :href="url">My Website</a>

  <p v-if="inventory > 10">In Stock</p>
  <p v-else-if="inventory > 0">Almost Sold Out</p>
  <p v-else>Out of Stock</p>

  <ul>
    <li v-for="(detail, index) in details" :key="index">{{ detail }}</li>
  </ul>

  <div v-for="variant in variants" :key="variant.id">{{ variant.color }}</div>
</template>
