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
      

          <div class="avatar-container" @mouseenter="showDropdown = true" @mouseleave="showDropdown = false">
            <div class="avatar">
              <el-avatar size="default" src="https://images.pexels.com/photos/33101/new-wing-emergency-at-the-moment.jpg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1" />
            </div>

            <!-- 浮窗动画 -->
            <transition name="fade">
            <!-- 浮窗内容 -->
             <div class="dropdown" v-if="showDropdown">
              <ul>
                <li @click="goToProfile">个人中心</li>
                <li @click="logout">退出</li>
              </ul>
             </div>
            </transition>
          </div>
        </div>
      </header>

</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import { useRouter } from 'vue-router';


export default defineComponent({
  name: 'RegisteredHomePageHeader',
  setup() {
    const router = useRouter();
    const showDropdown = ref(false);

    const goToProfile = () => {
      console.log('Go to profile');
    };

    const logout = () => {
      localStorage.removeItem('token'); //  清除登录状态
      router.push('/login');
    }

    return {
      showDropdown,
      goToProfile,
      logout
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


/* 头像部分 */
  .avatar {
    display: flex;
    padding: 12px;
  }

  /* 父容器 */
.avatar-container {
  position: relative;
  display: inline-block;
}

/* 浮窗样式 */
.dropdown {
  position: absolute;
  top: 60px;
  right: 0;
  background-color: #fff;
  box-shadow: 0px 2px 8px rgba(0, 0, 0, 0.1);
  border-radius: 12px;
  width: 120px;
  z-index: 100;
}

.dropdown ul {
  margin: 0;
  padding: 0;
  list-style: none;
}

.dropdown li {
  padding: 10px 16px;
  font-size: 14px;
  color: #333;
  cursor: pointer;
  transition: background-color 0.2s;
  border-radius: 12px;
}

.dropdown li:hover {
  background-color: #f5f5f5;
  border-radius: 12px;
}

/* 动画 */
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.3s ease;
}

.fade-enter-from, .fade-leave-to {
  opacity: 0;
}

</style>