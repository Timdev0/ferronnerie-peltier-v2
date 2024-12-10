<script setup>
import { RouterView } from 'vue-router'
import Navbar from './components/NavBar.vue'
import NavFooter from './components/NavFooter.vue'
</script>

<template>
  <Navbar />
  <!-- <header>
    <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />

      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
    </div>
  </header> -->

  <RouterView class="main-content" />

  <NavFooter />
</template>

<style scoped lang="scss">
.main-content {
  flex-grow: 1;
}
</style>
