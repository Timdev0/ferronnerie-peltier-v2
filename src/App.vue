<script setup>
import { RouterView } from 'vue-router'
import Navbar from './components/NavBar.vue'
import NavFooter from './components/NavFooter.vue'
</script>

<template>
  <Navbar />

  <RouterView class="main-content" />

  <NavFooter />
</template>

<style scoped lang="scss">
.main-content {
  flex-grow: 1;
  padding: 2rem 6rem;
}
</style>
