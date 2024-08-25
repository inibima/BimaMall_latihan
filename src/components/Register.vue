<template>
  <div class="register">
    <h1>Daftar Akun Baru</h1>
    <form @submit.prevent="register">
      <div class="form-group">
        <label for="username">Username:</label>
        <input type="text" id="username" v-model="username" required>
      </div>
      <div class="form-group">
        <label for="email">Email:</label>
        <input type="email" id="email" v-model="email" required>
      </div>
      <div class="form-group">
        <label for="password">Password:</label>
        <input type="password" id="password" v-model="password" required>
      </div>
      <button type="submit">Daftar</button>
    </form>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'Register',
  data() {
    return {
      username: '',
      email: '',
      password: ''
    };
  },
  methods: {
    async register() {
      try {
        await axios.post('http://localhost:5000/api/users/register', {
          username: this.username,
          email: this.email,
          password: this.password
        });

        // Login otomatis setelah pendaftaran
        await this.login();

        // Redirect ke halaman dashboard
        this.$router.push('/dashboard');
      } catch (error) {
        console.error('Error during registration:', error.response.data);
      }
    },
    async login() {
      try {
        await axios.post('http://localhost:5000/api/users/login', {
          email: this.email,
          password: this.password
        });
      } catch (error) {
        console.error('Error logging in:', error.response.data);
      }
    }
  }
};
</script>

<style scoped>
.register {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 2rem;
}

.form-group {
  margin-bottom: 1rem;
}

form {
  display: flex;
  flex-direction: column;
}

label {
  margin-bottom: 0.5rem;
}

input {
  padding: 0.5rem;
  font-size: 1rem;
  border: 1px solid #ccc;
  border-radius: 5px;
}

button {
  padding: 0.7rem;
  font-size: 1rem;
  color: white;
  background-color: #333;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background-color: #555;
}
</style>