<script setup>
import axios from 'axios';
import { ref, onMounted } from 'vue'
import {toast} from 'vue3-toastify';

const products = ref([])

onMounted(() => {
 // toast.info('Termékek letöltve!')
  axios.get('http://localhost:3000/products')
  .then(resp => products.value = resp.data)
  .then (toast.info('Termékek letöltve!'))
})
</script>

<template>
  <h1>Termékek</h1>
</template>
