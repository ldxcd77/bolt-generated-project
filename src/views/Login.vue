<script setup lang="ts">
import { ref } from 'vue'
import { useRouter } from 'vue-router'
import { useAuthStore } from '../store/auth'
import { ElForm, ElFormItem, ElInput, ElButton, ElLink } from 'element-plus'

const router = useRouter()
const authStore = useAuthStore()

const form = ref({
  username: '',
  password: ''
})

const handleLogin = () => {
  authStore.login()
  router.push('/home')
}
</script>

<template>
  <div class="login-container">
    <div class="logo">
      <!-- Replace with your logo -->
      <img src="/src/assets/logo.png" alt="Logo" />
    </div>
    <ElForm :model="form" class="login-form">
      <h2>Login</h2>
      <ElFormItem label="Username">
        <ElInput v-model="form.username" placeholder="Enter username" />
      </ElFormItem>
      <ElFormItem label="Password">
        <ElInput
          v-model="form.password"
          type="password"
          placeholder="Enter password"
        />
      </ElFormItem>
      <ElButton type="primary" @click="handleLogin">Login</ElButton>
      <div class="register-link">
        Don't have an account?
        <ElLink href="/register" type="primary">Register here</ElLink>
      </div>
    </ElForm>
  </div>
</template>

<style scoped>
.login-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: #f5f7fa; /* Light background */
}

.logo img {
  width: 100px;
  margin-bottom: 2rem;
}

.login-form {
  width: 300px;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  background-color: #fff; /* White form background */
}

h2 {
  text-align: center;
  margin-bottom: 20px;
  color: #333; /* Dark text for headings */
}

.el-form-item__label {
  color: #555; /* Slightly darker text for labels */
}

.register-link {
  text-align: center;
  margin-top: 1rem;
  font-size: 0.9em;
}
</style>
