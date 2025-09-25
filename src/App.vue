<script setup>
import { ref, computed, onMounted, onUnmounted } from 'vue'
import { RouterView } from 'vue-router'
import Navbar from './components/NavBar.vue'
import NavFooter from './components/NavFooter.vue'
import { throttle } from '@/utils/throttle.js'


const navbarRef = ref(null);
const navbarHeight = ref(0);
const isScrolled = ref(false);

const mainMarginTop = computed(() => {
  return `${navbarHeight.value}px`;
});

let scrollTimeout;
const handleScroll = throttle(() => {
  isScrolled.value = window.scrollY > 0;
  clearTimeout(scrollTimeout);
  scrollTimeout = setTimeout(() => {
    isScrolled.value = window.scrollY > 0;
  }, 120);
}, 100);
onMounted(() => {
  if (navbarRef.value) {
    navbarHeight.value = navbarRef.value?.$el?.offsetHeight || 0;
  }
  window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<template>
  <Navbar ref="navbarRef" :isScrolled="isScrolled" />

  <RouterView class="main-content" :style="{ 'margin-top': mainMarginTop }" />

  <NavFooter />
</template>

<style scoped lang="scss">
.main-content {
  flex-grow: 1;
}
</style>
