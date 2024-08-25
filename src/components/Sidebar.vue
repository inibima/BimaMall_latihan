<template>
  <aside class="sidebar">
    <a :href="whatsappLink" target="_blank" class="whatsapp-link">
      <img src="https://img.icons8.com/color/48/000000/whatsapp.png" alt="WhatsApp" />
      <span class="tooltip">Call Center</span>
    </a>
  </aside>
</template>

<script>
export default {
  name: 'Sidebar',
  computed: {
    whatsappLink() {
      return `https://wa.me/085700000000`;
    }
  }
};
</script>

<style scoped>
.sidebar {
  width: 50px; /* Small width for hidden state */
  height: 50px; /* Height of the icon */
  position: fixed;
  right: 0;
  top: 100px; /* Adjust based on where you want it to appear */
  background-color: #f4f4f4;
  box-shadow: -2px 0 5px rgba(0, 0, 0, 0.1);
  transition: width 0.3s;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
}

.sidebar:hover {
  width: 150px; /* Expanded width on hover */
}

.whatsapp-link {
  display: flex;
  align-items: center;
  text-decoration: none;
  color: #25d366;
}

.whatsapp-link img {
  margin-right: 0.5rem;
}

.tooltip {
  opacity: 0;
  white-space: nowrap;
  transition: opacity 0.3s;
}

.sidebar:hover .tooltip {
  opacity: 1;
}
</style>