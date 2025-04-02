<template>
  <footer class="footer" role="contentinfo">
    <div class="footer__grid">
      <RouterLink class="footer__link" to="/mentions-legales" active-class="active-link" aria-label="Mentions légales">
        Mentions légales
      </RouterLink>
      <p class="footer__text">
        Copyright © Ferronnerie PELTIER {{ year }}
      </p>
    </div>
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
  display: grid;
  align-items: center;
  font-size: 1rem;

  @media screen and (max-width: 768px) {
    padding: 0.5rem;
    font-size: 0.8rem;
  }

  .active-link {
    text-decoration: none;

    &::after {
      background-color: var(--color-white);
      width: 100%;
    }
  }

  &__grid {
    display: grid;
    grid-template-columns: 1fr auto 1fr;
    align-items: center;
    width: 100%;
    padding: 0.5rem;

    @media screen and (max-width: 768px) {
      padding: 0;
      grid-template-columns: 1fr 1fr;

    }
  }

  &__text {
    text-align: center;
    margin: 0;
  }

  &__link {
    color: var(--color-white);
    text-decoration: none;
    position: relative;
    transition: color 0.3s ease-in-out;
    width: fit-content;

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
      background-color: var(--color-gold);
    }
  }

}
</style>
