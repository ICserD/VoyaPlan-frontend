<!-- HomePage Header -->
<template>
  <!-- 顶部导航栏 -->
      <header class="navbar">
        <div class="navbar-left">
          <h1 class="logo">MD</h1>
        </div>
        <div class="navbar-right">
          <el-menu
            class="el-menu-demo"
            mode="horizontal"
            :ellipsis="false"
            >
            <el-menu-item index="1">旅游圈</el-menu-item>
            <el-menu-item index="1">旅行规划</el-menu-item>
            <el-menu-item index="1">联系我们</el-menu-item>

          </el-menu>
          <el-button class="ButtonWhite" size="small" @click="onLogin">登录</el-button>
          <el-button class="ButtonBlack" size="small" type="success" @click="onRegister">注册</el-button>
        </div>
      </header>

</template>

<script lang="ts">
import { defineComponent } from 'vue';


export default defineComponent({
  name: 'HomePageHeader',
  setup() {
    const onLogin = () => {
      console.log('点击登录');
    };

    const onRegister = () => {
      console.log('点击注册');
    };

    return {
      onLogin,
      onRegister,
    };
  },
});
</script>

<style scoped>
/* 顶部导航栏 */
 .navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px 50px;
    background-color: white;
    box-shadow: 0px 2px 8px rgba(0, 0, 0, 0.1);
  }
  
  .logo {
    font-size: 24px;
    font-weight: bold;
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
    /* margin-left: 10px; */
    display: flex;
    /* width: 64px; */
    /* height: 30px; */
    /* padding: 13px 27px; */
    justify-content: space-between;
    /* align-items: center; */
    /* gap: 10px; */
    /* border-radius: 12px; */
    /* background: #EAEAEA; */
  }
</style>