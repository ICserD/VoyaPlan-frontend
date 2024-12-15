<!-- HomePage Header -->
<template>
  <!-- 顶部导航栏 -->
      <header class="navbar">
        <div class="navbar-left">
          <h1 class="logo">MD</h1>
        </div>
        <div class="navbar-right">

          <ul class="navbar-item">
            <router-link to="/" class="navbar-link">旅游圈</router-link>
            <router-link to="/" class="navbar-link">旅游规划</router-link>
            <router-link to="/" class="navbar-link">关于我们</router-link>
          </ul>
      

          <div class="ButtonArea">
            <button class="ButtonWhite" @click="$emit('login')">登录</button>
            <button class="ButtonBlack" @click="$emit('register')">注册</button>
          </div>
        </div>
      </header>

</template>

<script lang="ts">
import { defineComponent } from 'vue';


export default defineComponent({
  name: 'HomePageHeader',
  emits: ['login', 'register']
});
</script>

<style scoped>
/* 顶部导航栏 */
 .navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 24px;
    background-color: white;
    box-shadow: 0px 2px 8px rgba(0, 0, 0, 0.1);
  }

  .nav-list {
    display: flex;
    list-style-type: none;
    padding: 0;
    margin: 0;
  }
  .logo {
    color: #000;
    text-align: center;
    text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
    font-family: jsMath-cmsy10;
    font-size: 26px;
    font-style: normal;
    font-weight: 500;
    line-height: 100%; /* 26px */
  }
  
  .menu {
    display: flex;
    gap: 20px;
  }
  
  .nav-list {
    display: flex;
    justify-content: space-between;

  }

  .navbar-right {
    display: flex;
    justify-content: space-between;
    gap: 64px;
  }

  .ButtonArea {
    display: flex;
    justify-content: space-between;
    gap: 12px;
  }

  .navbar-item {
    /* margin-right: 30px; */
    display: flex;
    align-items: center;
    list-style: none;
    margin: 0;
    padding: 0;
    gap: 32px;
  }

.navbar-link {
  text-decoration: none;
  color: #333;
  font-size: 16px;
  font-weight: 400;
  line-height: 100%;
  position: relative;
  transition: color 0.3s ease;
}

.navbar-link:hover {
  color: #87898b;
}

.navbar-link::after {
  content: '';
  position: absolute;
  left: 0;
  bottom: 0;
  width: 100%;
  height: 2px;
  background-color: #a9acaf;
  transform: scaleX(0);
  transform-origin: bottom right;
  transition: transform 0.3s ease;
}

.navbar-link:hover::after {
  transform: scaleX(1);
  transform-origin: bottom left;
}

</style>