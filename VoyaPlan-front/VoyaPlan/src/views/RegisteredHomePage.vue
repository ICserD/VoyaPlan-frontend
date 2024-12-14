<template>
    <div class="CommonContainer">
        <RegisteredHomePageHeader class="Header"/>
        <HomePageMain class="Main"/>
        <HomePageFooter class="Footer"/>        
    </div>
</template>

<script setup lang="ts">
import { defineComponent } from 'vue';
import RegisteredHomePageHeader from '@/components/RegisteredHomePageHeader.vue';
import HomePageMain from '../components/HomePageMain.vue';
import HomePageFooter from '../components/HomePageFooter.vue';

defineComponent({
    name: 'HomePage'
});
</script>

<style scoped>
.CommonContainer {
    display: flex;
    flex-direction: column;
    height: 100vh;
}

.RegisteredHeader {
  flex: 1;
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