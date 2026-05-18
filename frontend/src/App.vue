<template>
  <div>
    <h1>Hello Vue 3 + Vite!</h1>
    <button @click="fetchPing">Ping FastAPI</button>
    <p v-if="result">后端返回: {{ result }}</p>
  </div>
</template>

<script setup>
import { ref } from 'vue'
const result = ref("")
async function fetchPing() {
  const res = await fetch('http://127.0.0.1:8000/api/ping')
  const data = await res.json()
  result.value = data.message
}
</script>
