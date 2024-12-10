<template>
  <footer class="footer" role="contentinfo">
    <p class="footer__text">
      Copyright © Ferronnerie PELTIER {{ year }}
    </p>
    <RouterLink class="footer__link" to="/mentions-legales" active-class="active-link" aria-label="Mentions légales">
      Mentions légales
    </RouterLink>
  </footer>
</template>

<script setup>
import { ref } from 'vue'
import { RouterLink } from 'vue-router'

const year = ref(new Date().getFullYear())
</script>

<style scoped lang="scss">
.footer {
  background-color: var(--color-primary);
  color: var(--color-white);
  padding: 1rem 6rem;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;

  &__text {
    flex-grow: 1;
    text-align: center;
  }


  .active-link {
    text-decoration: none;

    &::after {
      background-color: var(--color-white);
      width: 100%;
    }
  }

  &__link {
    color: var(--color-white);
    text-decoration: none;
    position: relative;
    transition: color 0.3s ease-in-out;
    margin-left: auto;

    &:hover {
      color: var(--color-gold);
    }

    &::after {
      content: '';
      position: absolute;
      left: 0;
      bottom: -0.3rem;
      width: 0;
      height: 2px;
      background-color: var(--color-gold);
      transition: width 0.3s ease-in-out;
    }

    &:hover::after {
      width: 100%;
      background-color: (var(--color-gold));
    }
  }

}
</style>
