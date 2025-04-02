<template>
  <header class="navbar" role="banner">
    <nav class="navbar__nav" role="navigation" aria-label="Navigation Principale">
      <div class="navbar__nav__left">
        <img class="home-icon" src="/src/assets/favicon.ico/" alt="Ferronnerie Peltier Logo" aria-hidden="true" />
        <RouterLink class="navbar__nav__left__link navbar__nav__link" to="/" active-class="active-link"
          aria-label="Aller à la page d'accueil">
          <span>Ferronnerie Peltier</span>
        </RouterLink>
      </div>
      <div class="navbar__nav__right">
        <RouterLink class="navbar__nav__right__link navbar__nav__link" to="/galerie" active-class="active-link"
          aria-label="Aller à la galerie">
          Galerie
        </RouterLink>
        <RouterLink class="navbar__nav__right__link navbar__nav__link" to="/contact" active-class="active-link"
          aria-label="Aller à la page de contact">
          Contact
        </RouterLink>
      </div>
    </nav>
  </header>
</template>
<script setup>
import { RouterLink } from 'vue-router'

</script>


<style scoped lang="scss">
.navbar {
  background-color: var(--color-primary);
  color: var(--color-white);
  z-index: 2;

  .active-link {
    text-decoration: none;

    &::after {
      background-color: var(--color-white);
      width: 100%;
    }
  }

  &__nav {
    padding: 2rem 6rem;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;

    @media screen and (max-width: 768px) {
      padding: 0.5rem 0.5rem;
    }

    &__left {
      display: flex;
      flex-direction: row;
      gap: 1rem;
      justify-content: center;
      align-items: center;

      &__link {
        font-size: 1.5rem;
        font-family: 'Cinzel', serif;
        font-weight: 500;

        @media screen and (max-width: 768px) {
          font-size: 1rem;
        }
      }
    }

    &__right {
      display: flex;
      flex-direction: row;
      gap: 1rem;
      align-items: center;
      font-size: 1rem;
    }

    &__link {
      color: var(--color-white);
      text-decoration: none;
      position: relative;
      transition: color 0.3s ease-in-out;

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

  .home-icon {
    width: 2rem;
    height: 2rem;

    @media screen and (max-width: 768px) {
      display: none;
    }
  }


}
</style>
