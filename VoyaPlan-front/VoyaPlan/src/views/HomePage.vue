<template>
    <div class="CommonContainer">
        <HomePageHeader class="Header" @login="handleLogin" @register="handleRegister" />
        <HomePageMain class="Main"/>
        <HomePageFooter class="Footer"/>        
    </div>
</template>

<script setup lang="ts">
import { defineComponent } from 'vue';
import HomePageHeader from '../components/HomePageHeader.vue';
import HomePageMain from '../components/HomePageMain.vue';
import HomePageFooter from '../components/HomePageFooter.vue';
import { useRouter } from 'vue-router';

defineComponent({
    name: 'HomePage'
});

const router = useRouter();

const handleLogin = () => {
  router.push('/login');
};

const handleRegister = () => {
  router.push('/register');
};

</script>

<style scoped>
.CommonContainer {
    display: flex;
    flex-direction: column;
    height: 100vh;
}

.Header {
    flex : 1;
    align-items: center;
}


.Main {
    flex : 14;
}

.Footer {
    flex : 1;
    align-items: center;
    justify-content: center;
    display: flex;
}
</style>