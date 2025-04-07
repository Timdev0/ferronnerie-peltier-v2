<template>
  <div class="not-found">
    <section>
      <h1>404 - Page introuvable </h1>
      <p>La page que vous cherchez est introuvable.</p>
      <router-link aria-label="Retourner à l'accueil" to="/">Retourner à l'accueil</router-link>
    </section>
  </div>
</template>

<style scoped lang="scss">
section {
  padding: 2rem 10rem;

  @media screen and (max-width: 768px) {
    padding: 2rem;
  }
}
</style>
