<template>
    <form @submit.prevent="submitForm" class="p-4 max-w-md mx-auto space-y-4">
      <div class="container">
        <h1>Dodaj przystanek</h1>
      <div>
        <label for="number" class="block font-semibold">Numer rejestracyjny:</label><br>
        <input
          id="number"
          v-model="bus.number"
          type="text"
          class="w-full border rounded px-3 py-2"
          required
        />
      </div>
      <div>
        <label for="longi" class="block font-semibold">Longi:</label><br>
        <input
          id="longi"
          v-model="bus.longi"
          type="text"
          class="w-full border rounded px-3 py-2"
          required
        />
      </div>
      <div>
        <label for="latki" class="block font-semibold">Latki:</label><br>
        <input
          id="latki"
          v-model="bus.latki"
          type="text"
          class="w-full border rounded px-3 py-2"
          required
        />
      </div>
  
     
  
      <div>
        <label for="ulica" class="block font-semibold">Ulica:</label><br>
        <input
          id="ulica"
          v-model="bus.ulica"
          type="text"
          class="w-full border rounded px-3 py-2"
          required
        />
      </div>
  
      <button
        type="submit"
        class="bg-blue-600 text-white px-4 py-2 rounded hover:bg-blue-700"
      >
        Dodaj przystanek
      </button>
      </div>
    </form>
  </template>
  
  <script setup>
  import { reactive } from 'vue'
  
  const bus = reactive({
    number: '',
    brand: '',
    model: ''
  })
  
  const submitForm = () => {
    console.log('Dodano autobus:', bus)
    // Możesz tu zamiast tego wysłać dane np. do API
  }
  </script>
  
  <style scoped>
  .container{
    background-color: var(--moj_srodek); /* Kolor tła kontenera */
    border-radius: 15px; /* Zaokrąglone rogi */
  }
form {                     
  transform: translateX(-50%);          
  background-color: var(--moj_szary);   
  padding: 20px;                        
  border-radius: 15px;                  
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2); 
  height: auto;                         
  width: 90%;                          
  display: flex;                        
  flex-direction: column;   
  margin-top: 10%;         
}

input{
  width: 80%;                         
  padding: 10px;    
  margin: 10px;                    
  border-radius: 8px;                  
  border: 1px solid #ccc;               
  font-size: 16px;                      
}

select {
    width: 85%;                          
  padding: 10px;                      
  border-radius: 8px;                   
  border: 1px solid #ccc;               
  font-size: 16px;                      
}
button{
width: 83%;                         /* Szerokość pól formularza i przycisków */
  padding: 10px;                        /* Wewnętrzne marginesy */
  border-radius: 8px;                   /* Zaokrąglone rogi */
  border: 1px solid #ccc;               /* Lekka ramka */
  font-size: 16px; 
  height: 50px;
}

input:focus, select:focus, button:focus {
  outline: none;                        /* Usuwamy domyślną ramkę przy focusu */
  border-color: #4CAF50;                /* Kolor ramki przy focusu */
}

button {
  background-color: var(--moj_zielony);            /* Kolor przycisku */
  color: white;                         /* Kolor tekstu w przycisku */
  border: none;                          /* Usuwamy ramkę */
  cursor: pointer;                      /* Kursor wskazujący na kliknięcie */
  transition: background-color 0.3s ease; /* Płynna zmiana koloru tła */
}

button:hover {
  background-color: #45a049;            /* Kolor tła przycisku po najechaniu */
}

button:active {
  background-color: #388e3c;            /* Kolor tła przycisku po kliknięciu */
}

label {
  font-size: 24px;                      /* Rozmiar czcionki dla etykiet */
  color: white;                          /* Kolor etykiet */
}

select {
  background-color: #f9f9f9;            /* Tło dla menu wyboru */
}
  </style>
  