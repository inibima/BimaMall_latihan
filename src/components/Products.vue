<template>
  <div class="products">
    <h1>Daftar Produk</h1>
    <div class="product-list">
      <div class="product-item" v-for="product in products" :key="product.name">
        <img :src="product.image" :alt="product.name">
        <div class="product-info">
          <p>{{ product.name }}</p>
          <p class="price" @click="buyProduct(product)">Rp {{ product.price.toLocaleString('id-ID') }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Products',
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
  },
  methods: {
    buyProduct(product) {
      alert(`Anda membeli ${product.name} seharga Rp ${product.price.toLocaleString('id-ID')}`);
    }
  }
};
</script>

<style scoped>
.products {
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
  border: 1px solid #ddd;
  padding: 1rem;
  border-radius: 10px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.product-item img {
  width: 200px;
  height: 300px;
  object-fit: cover;
  border-radius: 10px;
}

.product-info {
  text-align: center;
}

.price {
  margin-top: 0.5rem;
  font-size: 1.2rem;
  color: #e74c3c;
  cursor: pointer;
  text-decoration: underline;
}

.price:hover {
  color: #c0392b;
}
</style>