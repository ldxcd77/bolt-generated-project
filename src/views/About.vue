<script setup lang="ts">
import { useRouter } from 'vue-router'
import { ElButton, ElMessage } from 'element-plus'

const router = useRouter()

const showMessage = () => {
  ElMessage.success('This is a success message!')
}
</script>

<template>
  <div class="about">
    <h1>About Page</h1>
    <ElButton @click="router.push('/')" type="primary">
      Go to Home
    </ElButton>
    <ElButton @click="showMessage" type="success">
      Show Message
    </ElButton>
  </div>
</template>

<style scoped>
.about {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
</style>
