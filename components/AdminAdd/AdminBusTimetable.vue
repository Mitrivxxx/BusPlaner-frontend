<template>
    <form @submit.prevent="submitForm" class="p-4 max-w-md mx-auto space-y-4">
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
form {
  position: absolute;                  /* Pozwala na pozycjonowanie poza kontenerem */
  top: 100px;                           /* Zmiana wartości pozwala na dostosowanie odległości od góry */
  left: 180%;                            /* Wyrównanie komponentu w poziomie */
  transform: translateX(-50%);          /* Dokładne wyśrodkowanie */
  background-color: var(--moj_szary);   /* Kolor tła formularza */
  padding: 20px;                        /* Wewnętrzne marginesy */
  border-radius: 15px;                  /* Zaokrąglone rogi formularza */
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2); /* Wyraźniejszy cień */
  
  margin-top: -240px;                   /* Ustawienie marginesu górnego */
  height: auto;                         /* Zmieniamy wysokość, aby dopasować się do zawartości */
  width: 90%;                           /* Szerokość formularza - dostosowana do rozmiaru ekranu */
  
  display: flex;                        /* Używamy flexboxa do ułożenia elementów */
  flex-direction: column;               /* Układ pionowy */
  gap: 15px;                            /* Przerwa między elementami formularza */
}

input{
  width: 80%;                          /* Szerokość pól formularza i przycisków */
  padding: 10px;                        /* Wewnętrzne marginesy */
  border-radius: 8px;                   /* Zaokrąglone rogi */
  border: 1px solid #ccc;               /* Lekka ramka */
  font-size: 16px;                      /* Rozmiar czcionki */
}
select {
    width: 85%;                          /* Szerokość pól formularza i przycisków */
  padding: 10px;                        /* Wewnętrzne marginesy */
  border-radius: 8px;                   /* Zaokrąglone rogi */
  border: 1px solid #ccc;               /* Lekka ramka */
  font-size: 16px;                      /* Rozmiar czcionki */
}
button{
width: 85%;    
margin-left: 8%;                      /* Szerokość pól formularza i przycisków */
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
  