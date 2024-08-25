<template>
  <header class="header">
    <h1>BimaMall</h1>
    <nav class="nav">
      <ul class="nav-links">
        <li><router-link to="/home">Beranda</router-link></li>
        <li><router-link to="/products">Produk</router-link></li>
        <li><router-link to="/register">Daftar</router-link></li>
        <li><router-link to="/dashboard">Dashboard</router-link></li>
        <li><a @click="logout">Logout</a></li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'Header',
  methods: {
    logout() {
      localStorage.removeItem('auth');
      this.$router.push('/');
    }
  }
};
</script>

<style scoped>
.header {
  background-color: #444;
  color: white;
  padding: 1rem;
  text-align: center;
}

.header h1 {
  margin: 0;
  font-size: 2rem;
}

.nav {
  margin-top: 1rem;
}

.nav-links {
  list-style: none;
  display: flex;
  justify-content: center;
  gap: 1rem;
}

.nav-links a {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}

.nav-links a:hover {
  text-decoration: underline;
}
</style>