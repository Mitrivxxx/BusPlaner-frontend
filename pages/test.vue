<script setup>
const message = ref("Kliknij przycisk, aby połączyć się z FastAPI")

const fetchData = async () => {
  try {
    const response = await fetch('http://localhost:8000/')
    const data = await response.json()
    message.value = data.message
  } catch (error) {
    message.value = "Błąd połączenia z backendem"
    console.error(error)
  }
}
</script>

<template>
  <div>
    <h1>Połączenie Nuxt.js 3 z FastAPI</h1>
    <p>{{ message }}</p>
    <button @click="fetchData">Pobierz dane</button>
  </div>
</template>