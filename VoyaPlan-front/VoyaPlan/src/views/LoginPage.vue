<template>

  <div class="login-page">
    <LoginPageLeft class="left"/>
    <LoginPageRight class="right"/>
  </div>

</template>

<script lang="ts">
import { defineComponent } from 'vue';
import LoginPageRight from '../components/LoginPageRight.vue';
import LoginPageLeft from '@/components/LoginPageLeft.vue';

export default defineComponent({
  name: 'LoginPage',
  components: {
    LoginPageLeft,
    LoginPageRight,
  },
});
</script>

<style scoped>

.login-page {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  height: 100vh;
}


.left {
  flex: 14;
}

.right {
    flex: 4;
}

</style>