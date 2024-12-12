<script setup>
</script>

<template>
  <main class="home">
    <h1>Ferronnerie d'Art - Serrurerie - Metallerie | Willy Peltier</h1>
    <h2>Présentation</h2>
    <div class="home__header">
      <div class="home__header__left">
        <p>
          Créée en 1982, notre ferronnerie familiale, située à Samoreau près de Fontainebleau, est spécialisée dans la
          création et la fabrication de pièces en métal sur-mesure. Forts de plusieurs décennies d’expérience, nous
          concevons des ouvrages uniques tels que des portails, verrières, vérandas, escaliers, rampes débillardées,
          portes
          d’entrée, et bien d’autres éléments de serrurerie et de ferronnerie décorative.
        </p>

        <p>
          Transmise de père en fils, notre expertise artisanale allie savoir-faire traditionnel et techniques modernes
          pour
          répondre aux besoins spécifiques de nos clients, particuliers comme professionnels. Chaque réalisation est
          pensée
          pour s'intégrer parfaitement à votre intérieur ou extérieur, en mettant en valeur l'esthétique et la
          durabilité
          du
          métal.
        </p>

        <p>
          N’hésitez pas à nous contacter pour discuter de votre projet ou demander un devis personnalisé. La Ferronnerie
          Peltier, c’est l’art du métal au service de vos envies !
        </p>
      </div>
      <div class="home__header__right">
        <p>Le feu et le fer au service de l'art</p>
        <img class="home__header__right__logo" src="/src/assets/imgs/peltier.jpg"
          alt="Logo de la ferronnerie Peltier" />
      </div>
    </div>
    <h2>Nos Créations</h2>
  </main>
</template>

<style scoped lang="scss">
.home {
  &__header {
    display: flex;
    flex-direction: row;
    gap: 2rem;

    &__left {
      width: 70%;
    }

    &__right {
      width: 30%;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;

      &__logo {
        width: 100%;
        height: auto;
      }
    }
  }
}
</style>
