<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import { ElButton } from 'element-plus'
</script>

<template>
  <header>
    <nav>
      <RouterLink to="/">
        <ElButton type="primary">Home</ElButton>
      </RouterLink>
      <RouterLink to="/about">
        <ElButton type="success">About</ElButton>
      </RouterLink>
    </nav>
  </header>

  <main>
    <RouterView />
  </main>
</template>

<style>
nav {
  padding: 1rem;
  background: #333;
  display: flex;
  gap: 1rem;
}

nav a {
  text-decoration: none;
}

main {
  padding: 2rem;
}
</style>
