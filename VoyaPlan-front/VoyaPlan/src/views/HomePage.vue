<!-- HomePage.vue -->
<template>
    <Header />
    <Main />
    <Footer />
  </template>
  
  <script lang="ts">
  import { defineComponent } from 'vue';
  import Header from '../components/HomePageHeader.vue';
  import Main from '../components/HomePageMain.vue';
  import Footer from '../components/HomePageFooter.vue';
  
  export default defineComponent({
    name: 'HomePage',
    components: {
      Header,
      Main,
      Footer,
    },
  });
  </script>
  
  <style scoped>
  /* 如果有任何全局样式，可以放在这里 */
  </style>
  