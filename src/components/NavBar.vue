<template>
  <header class="navbar">
    <nav class="navbar__nav">
      <div class="navbar__nav__left">
        <RouterLink class="navbar__nav__left__link navbar__nav__link" to="/" active-class="active-link">
          <HomeIcon class="home-icon" />
          <span>Ferronnerie Peltier</span>
        </RouterLink>
      </div>
      <div class="navbar__nav__right">
        <RouterLink class="navbar__nav__right__link navbar__nav__link" to="/gallery" active-class="active-link">
          Galerie
        </RouterLink>
        <RouterLink class="navbar__nav__right__link navbar__nav__link" to="/contact" active-class="active-link">
          Contact
        </RouterLink>
      </div>
    </nav>
  </header>
</template>

<script setup>
import { RouterLink } from 'vue-router'
import { HomeIcon } from '@heroicons/vue/24/solid'


</script>


<style scoped lang="scss">
.navbar {
  background-color: var(--color-primary);
  color: var(--color-white);

  &__nav {
    padding: 2rem 6rem;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;

    &__left {
      &__link {
        display: flex;
        flex-direction: row;
        gap: 1rem;
        justify-content: center;
        align-items: center;
        font-size: 1.5rem;
      }
    }

    &__right {
      display: flex;
      flex-direction: row;
      gap: 1rem;
      align-items: center;
    }

    &__link {
      color: var(--color-white);
      text-decoration: none;
    }
  }

  .home-icon {
    width: 2rem;
    height: 2rem;
  }

  .active-link {
    text-decoration: underline;
  }
}
</style>
