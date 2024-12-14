<!-- Footer.vue -->
<template>
    <footer class="footer">
      <p>VoyaPlan © 2024</p>
    </footer>
  </template>
  
  <script lang="ts">
  import { defineComponent } from 'vue';
  
  export default defineComponent({
    name: 'Footer',
  });
  </script>
  
  <style scoped>
  /* 保留 footer 相关的样式 */
    .footer {
    text-align: center;
    padding: 0;
    background-color: white;
    border-top: 1px solid #f0f0f0;
  }
  </style>
  