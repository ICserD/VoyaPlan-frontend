<template>

  <div class="login-page">
    <LoginPageLeft class="left"/>
    <RegisterPageRight class="right"/>
  </div>

</template>

<script lang="ts">
import { defineComponent } from 'vue';
import RegisterPageRight from '@/components/RegisterPageRight.vue';
import LoginPageLeft from '@/components/LoginPageLeft.vue';

export default defineComponent({
  name: 'RegisterPage',
  components: {
    LoginPageLeft,
    RegisterPageRight,
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