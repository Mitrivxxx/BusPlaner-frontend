<template>
    <!-- Pasek górny -->
    <Header />
    <div class="login-container">
      <h2 class="text-center">Rejestracja</h2>
      
      <form @submit.prevent="submitForm" class="login-form">

        <div class="form-group">
          <label for="login">Login</label>
          <input
            v-model="login"
            type="text"
            id="login"
            class="form-control"
            placeholder="Wprowadź login"
            required
          />
        </div>
        
        <div class="form-group">
          <label for="password">Hasło</label>
          <input
            v-model="password"
            type="password"
            id="password"
            class="form-control"
            placeholder="Wprowadź hasło"
            required
          />
        </div>
        
        <div class="form-group">
          <label for="confirmPassword">Potwierdź hasło</label>
          <input
            v-model="confirmPassword"
            type="password"
            id="confirmPassword"
            class="form-control"
            placeholder="Potwierdź hasło"
            required
          />
        </div>
  
        <div class="form-group">
          <button type="submit" class="btn btn-primary w-full">
            Zarejestruj się
          </button>
        </div>
      </form>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  import Header from '@/components/Header.vue'
  import { useRouter } from 'vue-router'
  
  const firstName = ref('')
  const lastName = ref('')
  const login = ref('')
  const password = ref('')
  const confirmPassword = ref('')
  const router = useRouter()
  
  const submitForm = () => {
    if (password.value !== confirmPassword.value) {
      alert('Hasła się nie zgadzają')
      return
    }
  
    // Przykładowa logika rejestracji
    console.log(`Zarejestrowano użytkownika: ${firstName.value} ${lastName.value}, login: ${login.value}`)
    router.push('/login')  // Po rejestracji przekierowanie na stronę logowania
  }
  </script>
  
  <style scoped>
/* Stylowanie paska górnego */
.login-container {
  max-width: 400px;
  margin: 0 auto;
  margin-top: 200px;
  padding: 30px;
  background-color: var(--moj_szary);
    color: white;
  border-radius: 12px;
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.1);
  text-align: center;
}

/* Formularz */
.login-form {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

/* Stylowanie dla inputów */
.login-form .form-group label {
  font-size: 1rem;
  font-weight: bold;
  color: white;
}

.login-form .form-group input {
  padding: 12px;
  font-size: 1rem;
  border-radius: 8px;
  border: 1px solid #ccc;
  margin-top: 5px;
  width: 100%;
  box-sizing: border-box;
  transition: border-color 0.3s ease;
}

/* Efekt focus na inputach */
.login-form .form-group input:focus {
  border-color: var(--moj_zielony);
  outline: none;
}

/* Przycisk logowania */
.login-form .btn {
  padding: 12px;
  background-color: var(--moj_zielony); /* Zielony kolor */
  color: white;
  border: none;
  border-radius: 8px;
  font-size: 2rem;
    width: 100%;
    height: auto;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

/* Efekt na przycisk */
.login-form .btn:hover {
  background-color: #45a049;
}

.text-center {
  margin-bottom: 20px;
  color: white;
}

/* Tło całej strony (dla każdej strony aplikacji) */
html, body {
  margin: 0;
  padding: 0;
  height: 100%;
  background-color: #dddddd; /* Jasne tło */
}

body {
  font-family: Arial, sans-serif;
}
</style>