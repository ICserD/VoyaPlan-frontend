<template>
    <div class="login-right">
        <!-- 标签部分 -->
        <div class="login-page-right-top">
            <h1 class="title">VoyaPlan</h1>
            <p class="subtitle" >Welcome</p>
        </div>

        <!-- 输入部分 -->
        <form @submit.prevent="handleLogin" class="login-page-right-middle" method="post">
            <p class="input-prompt">账号</p>
            <input v-model="account" class="login-input" type="text" placeholder="手机号或邮箱" name="account">
            <p class="input-prompt">密码</p>
            <input v-model="passWord" class="login-input" type="password" placeholder="请输入密码" name="passWord">
        </form>
        
        <!-- 帮助注册部分 -->
        <button @click="handleLogin" class="login-button">登录</button>
        <div class="help-info">
            <p>没有账号？</p>
            <span @click="goToRegister" style="cursor: pointer; color: darkturquoise;">现在注册</span>
        </div>

    </div>
</template>

<script setup lang="ts">
import { defineComponent, ref } from 'vue';
import { useRouter } from 'vue-router';
import axios from 'axios';
import { ElNotification } from 'element-plus';
import { apiPath } from '@/apiConfig';

defineComponent({
    name: 'LoginPageRight'
});

const router = useRouter();

const goToRegister = () => {
    router.push('/register');
}

const account = ref('');
const passWord = ref('');

const showNotification = (message: string, type: 'success' | 'warning' | 'error' | 'info') => {
    ElNotification({
        title: type === 'success' ? '成功' : '提示',
        message: message,
        type: type,
        duration: 1300,
        position: 'top-right',
    });
}


const handleLogin = async() => {
    // let resp = await axios.post(apiPath.login, {account: account.value, password: password.value});
    // showNotification('post的结果' + resp.data.data.token, 'info');
    try{
        const response = await axios.post(apiPath.login,
            {
                account: account.value,
                passWord: passWord.value
            }
        );
        if(response.data.data.token){
            // 登录成功, 保存token
            localStorage.setItem('token', response.data.data.token);
            showNotification('登录成功', 'success');
            
            setTimeout(() => {
                router.push('/registeredHome');
            }, 1000); // 1秒后跳转
        } else {
            // 登录失败, 显示错误信息
            showNotification('登录失败, 请检查您的账号和密码', 'error');
            console.log('登录失败');
        }
    } catch (error) {
        showNotification('登录出错，请稍后再试', 'error');
        console.log(error);
    }
}

</script>

<style scoped>
    .login-page-right-top {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        margin-bottom: 10%;
    }

    .login-page-right-middle {
        display: flex;
        flex-direction: column;
        /* align-items: center; */
        gap: 25px;
    }

    .help-info {
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: center;
        margin-bottom: 25%;
    }

    .login-right {
        display: flexbox;
        align-items: center;
        flex-direction: column;
        justify-content: center;
        padding: 0% 5%;
    }

    .title {
        color: #000;
        text-align: center;
        font-family: "Josefin Sans";
        font-size: 64px;
        font-style: italic;
        font-weight: 400;
        line-height: 100%; /* 48px */
        margin-bottom: 10%;
    }

    .subtitle {
        color: #515151;
        text-align: center;
        font-family: "Josefin Sans";
        font-size: 24px;
        font-style: italic;
        font-weight: 400;
        line-height: 100%; /* 18px */
        margin-bottom: 20%;
    }

    .login-input {
        width: 100%;
        height: 36px;
        border-radius: 12px;
        background: #EAEAEA;
        border: none;
        padding: 0 12px;
        /* margin-bottom: 12px; */
    }

    .input-prompt {
        color: #515151;
        text-align: left;
        font-family: "Josefin Sans";
        font-size: 16px;
        font-style: normal;
        font-weight: 400;
        line-height: 100%; /* 14px */
    }

    .login-button {
        margin-top: 20%;
        margin-bottom: 10%;

        display: flex;
        width: 100%;
        height: 36px;
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

    .login-button:hover {
        background: #333;
        transform: scale(1.005);
    }

    .login-button:active {
        transform: scale(0.95);
    }

</style>