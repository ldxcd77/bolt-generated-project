<script setup lang="ts">
import { useRouter } from 'vue-router'
import { useAuthStore } from '../store/auth'
import { ElButton, ElAlert } from 'element-plus'

const router = useRouter()
const authStore = useAuthStore()

const handleLogout = () => {
  authStore.logout()
  router.push('/login')
}
</script>

<template>
  <div class="home">
    <ElAlert title="Welcome to Home Page" type="info" show-icon />
    <ElButton @click="handleLogout" type="danger">Logout</ElButton>
  </div>
</template>

<style scoped>
.home {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  padding: 2rem;
}
</style>
