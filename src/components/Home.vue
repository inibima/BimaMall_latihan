<template>
  <div id="home">
    <Navbar />
    <h1>Beranda</h1>
    <input type="text" v-model="searchTerm" placeholder="Cari produk..." />
    <div class="product-list">
      <div v-for="product in filteredProducts" :key="product.name" class="product-item">
        <img :src="product.image" :alt="product.name">
        <p>{{ product.name }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from './Navbar.vue';

export default {
  name: 'Home',
  components: {
    Navbar
  },
  data() {
    return {
      searchTerm: '',
      products: [
        { name: 'Resident Evil 7', image: '/assets/resident-evil-7.jpg', tags: ['Resident Evil'] },
        { name: 'Resident Evil Village', image: '/assets/resident-evil-village.jpg', tags: ['Resident Evil'] },
        { name: 'Grand Theft Auto: San Andreas', image: '/assets/gta-san-andreas.jpg', tags: ['Grand Theft Auto'] },
        { name: 'The Elder Scrolls V: Skyrim', image: '/assets/skyrim.jpg', tags: ['The Elder Scrolls'] },
        { name: 'Cyberpunk 2077', image: '/assets/cyberpunk-2077.jpg', tags: ['Cyberpunk 2077'] },
        { name: 'Elden Ring', image: '/assets/elden-ring.jpg', tags: ['Elden Ring'] }
      ]
    };
  },
  computed: {
    filteredProducts() {
      if (this.searchTerm === '') {
        return this.products;
      }
      return this.products.filter(product =>
        product.tags.some(tag => tag.toLowerCase().includes(this.searchTerm.toLowerCase()))
      );
    }
  }
};
</script>

<style scoped>
#home {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 2rem 0;
}

input[type="text"] {
  margin-bottom: 2rem;
  padding: 0.5rem;
  font-size: 1rem;
  width: 80%;
  max-width: 400px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.product-list {
  display: flex;
  flex-wrap: wrap;
  gap: 2rem;
  justify-content: center;
}

.product-item {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.product-item img {
  width: 200px;
  height: 300px;
  object-fit: cover;
  border-radius: 10px;
}

.product-item p {
  margin-top: 0.5rem;
  font-size: 1.2rem;
  text-align: center;
}
</style>