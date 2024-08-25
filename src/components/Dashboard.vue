<template>
  <div class="dashboard">
    <h1>Dashboard</h1>
    <div class="product-list">
      <div class="product-item" v-for="product in products" :key="product.name">
        <img :src="product.image" :alt="product.name">
        <p>{{ product.name }}</p>
        <p class="price">Rp {{ product.price.toLocaleString('id-ID') }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Dashboard',
  data() {
    return {
      products: [
        { name: 'Resident Evil 7', image: '/assets/resident-evil-7.jpg', price: 250000 },
        { name: 'Resident Evil Village', image: '/assets/resident-evil-village.jpg', price: 300000 },
        { name: 'Grand Theft Auto: San Andreas', image: '/assets/gta-san-andreas.jpg', price: 200000 },
        { name: 'The Elder Scrolls V: Skyrim', image: '/assets/skyrim.jpg', price: 350000 },
        { name: 'Cyberpunk 2077', image: '/assets/cyberpunk-2077.jpg', price: 450000 },
        { name: 'Elden Ring', image: '/assets/elden-ring.jpg', price: 500000 }
      ]
    };
  }
};
</script>

<style scoped>
.dashboard {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 2rem;
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

.product-item .price {
  margin-top: 0.5rem;
  font-size: 1.2rem;
  color: #e74c3c;
}
</style>