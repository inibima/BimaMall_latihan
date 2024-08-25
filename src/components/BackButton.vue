<template>
  <button @click="goBack" class="back-button">
    &larr; Back
  </button>
</template>

<script>
export default {
  name: 'BackButton',
  methods: {
    goBack() {
      this.$router.back();
    }
  }
};
</script>

<style scoped>
.back-button {
  background-color: #444;
  color: white;
  border: none;
  padding: 0.5rem 1rem;
  cursor: pointer;
  border-radius: 5px;
  font-size: 1rem;
  position: fixed;
  left: 10px;
  top: 50%;
  transform: translateY(-50%);
}

.back-button:hover {
  background-color: #666;
}
</style>