<template>
  <div class="wrapper" id="app">
    <LoadingAnimation v-if="isLoading" />
    
    <div v-else>
      <NavBar />
      <main>
        <router-view />
      </main>
      <Footer />
    </div>
  </div>
</template>

<script>
import NavBar from '@/components/NavBar.vue';
import Footer from '@/components/Footer.vue';
import LoadingAnimation from '@/components/LoadingAnimation.vue';
import { onMounted, ref } from 'vue';
import AOS from 'aos';
import 'aos/dist/aos.css';

export default {
  components: {
    NavBar,
    Footer,
    LoadingAnimation,
  },

  name: 'App',
  setup() {
    const isLoading = ref(true);

    onMounted(() => {
      // Simulate a loading delay
      setTimeout(() => {
        isLoading.value = false;
        AOS.init({
          duration: 1000,      // Animation duration (in milliseconds)
          easing: 'ease-in-out', // Animation easing
          once: true,          // Whether the animation should only happen once
        });
      }, 6000); // Adjust the delay as needed
    });

    return { isLoading };
  },
};
</script>

<style src="./assets/css/styles.css"></style>
