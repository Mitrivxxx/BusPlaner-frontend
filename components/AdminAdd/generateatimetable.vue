<template>

    <div class="container">
      <form>
        <h1>FORMULARZ GENEROWANIA ROZKŁADU JAZDY</h1>
        <!-- 1. Wybór linii -->
        <div class="form-section">
          <h2>1. Wybór linii</h2>
          <label>
            Numer linii:
            <input type="text" placeholder="Wpisz numer linii">
          </label>
        </div>
  
        <!-- 2. Dane rozkładu -->
        <div class="form-section">
          <h2>2. Dane rozkładu</h2>
          <div class="date-inputs">
            <label>
              Data obowiązywania od:
              <input type="date">
            </label>
            <label>
              Data obowiązywania do:
              <input type="date">
            </label>
          </div>
        </div>
  
        <!-- 3. Godziny odjazdów -->
        <div class="form-section">
            <h2>3. Godziny odjazdów</h2>
    <table class="departures-table">
      <thead>
        <tr>
          <th>Przystanek początkowy</th>
          <th>Godzina</th>
          <th>Przystanek końcowy</th>
          <th>Akcje</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(departure, index) in departures" :key="index">
          <td><input v-model="departure.startStop" type="text" placeholder="Nazwa przystanku"></td>
          <td><input v-model="departure.time" type="text" placeholder="HH:MM"></td>
          <td><input v-model="departure.endStop" type="text" placeholder="Nazwa przystanku"></td>
          <td><button @click="removeDeparture(index)" type="button">Usuń</button></td>
        </tr>
      </tbody>
    </table>
    <button @click="addDeparture" type="button">Dodaj kolejny odjazd</button>
  </div>
  
        <!-- 4. Przypisanie brygady -->
        <div class="form-section">
          <h2>4. Przypisanie brygady</h2>
          <label>
            Numer brygady:
            <input type="text" placeholder="Wpisz numer brygady">
          </label>
          
          <label>
            Autobus (rejestracja/model):
            <input type="text" placeholder="Wpisz dane autobusu">
          </label>
          
          <label>
            Kierowca:
            <input type="text" placeholder="Wpisz imię i nazwisko kierowcy">
          </label>
        </div>
  
        <button type="submit">Zapisz rozkład jazdy</button>
      </form>
    </div>
  </template>
<script setup>
import { ref } from 'vue';

const departures = ref([
  { startStop: '', time: '', endStop: '' },
  { startStop: '', time: '', endStop: '' },
  { startStop: '', time: '', endStop: '' }
]);

const addDeparture = () => {
  departures.value.push({ startStop: '', time: '', endStop: '' });
};

const removeDeparture = (index) => {
  if (departures.value.length > 1) {
    departures.value.splice(index, 1);
  }
};
</script>
  <style scoped>
.container {
    position: absolute;
  background-color: var(--moj_szary);
  width: 130%;
  max-width: 800px;
  padding: 20px;
  font-family: Arial, sans-serif;
  
  /* Centrowanie kontenera */
  margin-left: 40%;
    margin-top: -150px;
  
  /* Centrowanie zawartości w kontenerze */
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
  
  h1 {
    text-align: center;
    color: #333;
    margin-bottom: 30px;
  }
  
  .form-section {
    margin-bottom: 30px;
    padding: 15px;
    background-color: #f5f5f5;
    border-radius: 5px;
  }
  
  h2 {
    margin-top: 0;
    color: #444;
    font-size: 1.2em;
  }
  
  label {
    display: block;
    margin-bottom: 15px;
    color:black;
  }
  
  input[type="text"],
  input[type="time"],
  select {
    width: 100%;
    padding: 8px;
    margin-top: 5px;
    border: 1px solid #ddd;
    border-radius: 4px;
  }
  
  .date-inputs {
    display: flex;
    gap: 20px;
  }
  
  .date-inputs label {
    flex: 1;
  }
  
  .departures-table {
    width: 100%;
    border-collapse: collapse;
    margin-bottom: 15px;
  }
  
  .departures-table th,
  .departures-table td {
    padding: 10px;
    border: 1px solid #ddd;
    text-align: left;
  }
  
  .departures-table input {
    width: 100%;
    box-sizing: border-box;
  }
  
  button {
    background-color: #4CAF50;
    color: white;
    padding: 10px 15px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    margin-top: 10px;
  }
  
  button:hover {
    background-color: #45a049;
  }
  h1{
    color: white;
  }
  th{
    color:black;
  }
  </style>