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

const handleScroll = throttle(() => {
  isScrolled.value = window.scrollY > 0;
}, 100);

let scrollTimeout;
const handleScrollEnd = () => {
  clearTimeout(scrollTimeout);
  scrollTimeout = setTimeout(() => {
    isScrolled.value = window.scrollY > 0;
  }, 120);
};

onMounted(() => {
  if (navbarRef.value) {
    navbarHeight.value = navbarRef.value?.$el?.offsetHeight || 0;
  }
  window.addEventListener('scroll', handleScroll);
  window.addEventListener('scroll', handleScrollEnd);
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
  window.removeEventListener('scroll', handleScrollEnd);
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
