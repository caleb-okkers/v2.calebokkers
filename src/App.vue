<template>
  <div class="wrapper" id="app">
    <NavBar/>
    <main>
      <router-view/>
    </main>
    <Footer/>
  </div>
  
</template>



<script>
import NavBar from '@/components/NavBar.vue'
import Footer from '@/components/Footer.vue'
import { onMounted } from 'vue';
import AOS from 'aos';
import 'aos/dist/aos.css';

export default {
  
  components: {
    NavBar,
    Footer
  },

  name: 'App',
  setup() {
    onMounted(() => {
      AOS.init({
        duration: 1000,   // Animation duration (in milliseconds)
        easing: 'ease-in-out', // Animation easing
        once: true,       // Whether the animation should only happen once
      });
    });
  },
}
</script>

<style src="./assets/css/styles.css">

</style>
