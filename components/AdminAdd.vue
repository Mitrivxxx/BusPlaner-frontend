<template>
  <div class="container">
    <div class="button-container">
      <button>Dodaj pracownika</button>
      <button @click="activeComponent='AddBus'">Dodaj autobus</button>
      <button @click="activeComponent='AdminBusTimetable'">Dodaj przystanek</button>
      <button @click="activeComponent='AddLines'">Dodaj linie</button>
    </div>
      <component :is="currentComponent" />
    </div>
  </template>
<!---------------------------->
<script setup>
import AddBus from '~/components/AdminAdd/AddBus.vue'
import AdminBusTimetable from '~/components/AdminAdd/AdminBusTimetable.vue'
import AddLines from '~/components/AdminAdd/AddLines.vue'
import { computed, ref } from 'vue'

const activeComponent = ref(null)

const currentComponent = computed(() => {
  if (activeComponent.value === 'AddBus') return AddBus
  if (activeComponent.value === 'AdminBusTimetable') return AdminBusTimetable
  if (activeComponent.value === 'AddLines') return AddLines
  return null
})
</script>
<!---------------------------->
  <style scoped>
  .container{
    position: relative; /* Tworzymy kontekst do pozycjonowania absolutnego */
    padding: 20px;
  }
  .button-container {
    display: flex;
    gap: 20px;
    justify-content: center;
    margin-top: 20px;
    flex-wrap: wrap;
  }
  button{
    width: 40%;
  }
  .btn:hover {
    background-color: #45a049; /* Zmiana koloru przycisku przy hover */
  }
  </style>