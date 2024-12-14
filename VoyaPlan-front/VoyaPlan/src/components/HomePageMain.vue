<!-- Main.vue -->
<template>
    <main class="hero-section">
      <div class="hero-content">
        <h1 class="title">VoyaPlan</h1>
        <p class="subtitle">世界那么大，我想去看看</p>
        <!-- <el-input
          v-model="searchInput"
          placeholder="请输入旅行的起点"
          size="large"
          class="input-box"
        />
        <el-button type="primary" size="large" class="search-button" @click="onSearch">
          确定
        </el-button> -->
        <div class="inputArea">
          <input
            v-model="searchInput"
            type="text"
            placeholder="请输入旅行的起点"
            class="input-box"
          />
          <button class="HomePageInputButton" @click="onSearch">确定</button>
        </div>
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
    /* font-size: 48px;
    font-weight: bold;
    margin-bottom: 10px; */
    color: #000;
    text-align: center;
    font-family: "Josefin Sans";
    font-size: 64px;
    font-style: italic;
    font-weight: 400;
    line-height: 100%; /* 48px */
    margin-bottom: 18px;
  }
  
  .subtitle {
    color: #515151;
    text-align: center;
    font-family: "Josefin Sans";
    font-size: 18px;
    font-style: italic;
    font-weight: 400;
    line-height: 100%; /* 18px */
    margin-bottom: 24px;
  }
  
  .input-box {
    width: 560px;
    height: 36px;
    border-radius: 12px;
    background: #EAEAEA;
    border: none;
    padding: 0 12px;
  }
  

  .inputArea {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 20px;
    /* margin-top: 20px;     */
  }

  .HomePageInputButton {
    display: flex;
    width: 64px;
    height: 40px;
    padding: 0;
    justify-content: center;
    align-items: center;
    gap: 10px;
    border-radius: 12px;
    border: none;
    background: #000;

    color: #FFF;
    text-align: center;
    font-family: "Istok Web";
    font-size: 14px;
    font-style: normal;
    font-weight: 400;
    line-height: 100%; /* 14px */

    cursor: pointer;
    transition: background 0.3s, transform 0.3s;
  }

  .HomePageInputButton:hover {
    background: #333;
    transform: scale(1.05);
  }

  .HomePageInputButton:active {
    transform: scale(0.95);
  }
  </style>
  