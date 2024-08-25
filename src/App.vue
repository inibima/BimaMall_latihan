<template>
  <div id="app">
    <Header v-if="showHeader" />
    <div :class="['content', { centered: !showHeader }]">
      <router-view />
      <Sidebar v-if="showHeader" />
    </div>
    <Footer />
  </div>
</template>

<script>
import { computed } from 'vue';
import { useRoute } from 'vue-router';
import Header from './components/Header.vue';
import Sidebar from './components/Sidebar.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'App',
  components: {
    Header,
    Sidebar,
    Footer
  },
  setup() {
    const route = useRoute();

    const showHeader = computed(() => {
      return !['/', '/register'].includes(route.path);
    });

    return { showHeader };
  }
};
</script>

<style>
.content {
  display: flex;
  justify-content: space-between;
  min-height: calc(100vh - 60px); /* Adjust based on header and footer height */
  padding-bottom: 60px; /* Adjust based on footer height */
}

.centered {
  justify-content: center;
  align-items: center;
  height: calc(100vh - 60px);
}
</style>