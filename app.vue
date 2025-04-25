<template>
  <NuxtPage />
</template>

<script setup>
import { useRouter } from 'vue-router'
import { onMounted } from 'vue'

// Gdy komponent 'app.vue' zostanie zamontowany, wykonaj przekierowanie
onMounted(() => {
  const router = useRouter()
  router.push('/')  // Przekierowanie do strony 'index.vue'
})
</script>

<style>
  :root {
    --moj_zielony: #4CAF50;
    --moj_zielony_hover: #45a049;
    --moj_szary: #333;
    --moj_tlo: #222020;
    --moj_srodek: rgb(59, 59, 59);
  }

  button {
    background-color: var(--moj_zielony);
    color: white;
    border: none;
    padding: 20px 30px;
    margin: 10px 0px 10px 0px;
    font-size: 24px;
    cursor: pointer;
    width: 80%;
    border-radius: 5px;
  }
  
  button:hover {
    background-color: var(--moj_zielony_hover);
  }
  body {
    background-color: var(--moj_tlo);
    color: white;
  }
</style>