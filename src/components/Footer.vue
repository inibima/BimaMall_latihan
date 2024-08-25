<template>
  <footer v-if="showFooter" :class="['footer', { hidden: !isVisible }]">
    <BackButton />
    <p>© 2024 BimaMall. All rights reserved.</p>
  </footer>
</template>

<script>
import BackButton from './BackButton.vue';
import { computed } from 'vue';
import { useRoute } from 'vue-router';

export default {
  name: 'Footer',
  components: {
    BackButton
  },
  data() {
    return {
      lastScroll: 0,
      isVisible: true
    };
  },
  setup() {
    const route = useRoute();

    const showFooter = computed(() => {
      return !['/', '/register'].includes(route.path);
    });

    return { showFooter };
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll() {
      const currentScroll = window.pageYOffset;
      this.isVisible = currentScroll > this.lastScroll || currentScroll === 0;
      this.lastScroll = currentScroll;
    }
  }
};
</script>

<style scoped>
.footer {
  background-color: #333;
  color: white;
  padding: 1rem;
  display: flex;
  justify-content: center;
  align-items: center;
  position: fixed;
  bottom: 0;
  width: 100%;
  box-shadow: 0 -2px 5px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s;
  transform: translateY(0);
}

.footer.hidden {
  transform: translateY(100%);
}

.footer p {
  margin: 0;
  margin-left: 1rem;
}
</style>