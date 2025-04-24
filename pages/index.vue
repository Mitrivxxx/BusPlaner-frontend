<template>
    <div>
      <!-- Pasek górny -->
      <Header />
  
      <!-- Reszta strony -->
      <main class="main-content">
        <aside>
          <p class="text">Admin panel</p>
          <!-- Przyciski wyświetlają się tylko jeśli nie został załadowany komponent -->
          <button v-if="!isComponentLoaded" @click="loadComponent(AdminDodaj)">Dodaj</button>
          <button v-if="!isComponentLoaded" @click="loadComponent(AsideMain)">Wygeneruj rozkład jazdy</button>
  
          <!-- Dynamiczne ładowanie komponentów -->
          <component :is="currentComponent" v-if="isComponentLoaded" />
          <!-- Przycisk cofnij -->
          <button v-if="isComponentLoaded" @click="goBack">Cofnij</button>
        </aside>
  
      </main>
  
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  import Header from '@/components/Header.vue';
  import AdminDodaj from '@/components/AdminAdd.vue';

  // Referencja do aktualnie wyświetlanego komponentu
  const currentComponent = ref(null)
  
  // Stan do kontroli, czy komponent został załadowany
  const isComponentLoaded = ref(false)
  
  // Funkcja ładowania komponentu
  const loadComponent = (component) => {
    currentComponent.value = component
    isComponentLoaded.value = true
  }
  // Funkcja do cofania (resetowania stanu)
  const goBack = () => {
    currentComponent.value = null
    isComponentLoaded.value = false
  }
  
  </script>
  
  <style scoped>
  /* Stylowanie reszty strony */
  .text {
    font-size: 50px;
    padding-top: 40px;
    color: white;
  }
  
  .main-content {
    padding: 20px;
    margin-top: 20px;
    color: white;
  }
  
  aside {
    background-color: var(--moj_szary);
    height: auto;
    width: 30%;
    height: 600px;
    text-align: center;
    align-items: center;
  }
  </style>