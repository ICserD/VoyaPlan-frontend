<!-- Main.vue -->
<template>
    <main class="hero-section">
      <div class="hero-content">
        <h1 class="title">VoyaPlan</h1>
        <p class="subtitle">世界那么大，我想去看看</p>
        <el-input
          v-model="searchInput"
          placeholder="请输入旅行的起点"
          size="large"
          class="input-box"
        />
        <el-button type="primary" size="large" class="search-button" @click="onSearch">
          确定
        </el-button>
      </div>
    </main>
  </template>
  
  <script lang="ts">
  import { defineComponent, ref } from 'vue';
  
  export default defineComponent({
    name: 'HomePageMain',
    setup() {
      const searchInput = ref<string>('');
  
      const onSearch = () => {
        console.log('搜索目的地：', searchInput.value);
      };
  
      return {
        searchInput,
        onSearch,
      };
    },
  });
  </script>
  
  <style scoped>
  /* 保留 main 相关的样式 */
  .hero-section {
    background-image: url('https://images.pexels.com/photos/775687/pexels-photo-775687.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1'); /* 替换为实际图片链接 */
    background-size: cover;
    background-position: center;
    height: 500px;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    color: white;
    text-align: center;
  }
  
  .title {
    font-size: 48px;
    font-weight: bold;
    margin-bottom: 10px;
  }
  
  .subtitle {
    font-size: 20px;
    margin-bottom: 20px;
  }
  
  .input-box {
    width: 400px;
    margin-bottom: 20px;
  }
  
  .search-button {
    width: 100px;
  }
  </style>
  