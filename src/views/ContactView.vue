<script setup>
import { ref, onMounted } from 'vue';
import ModalCustom from '@/components/ModalCustom.vue'

const isMapEnabled = ref(false);
const isModalOpen = ref(false)

onMounted(() => {
  const storedValue = localStorage.getItem('isMapEnabled');
  isMapEnabled.value = storedValue ? JSON.parse(storedValue) : false;
})

const toggleMap = () => {
  isMapEnabled.value = !isMapEnabled.value;
  localStorage.setItem('isMapEnabled', JSON.stringify(isMapEnabled.value));
}

const toggleModal = () => {
  isModalOpen.value = !isModalOpen.value;
}

const acceptWarning = () => {
  toggleMap();
  toggleModal();
}

</script>


<template>
  <div class="contact">
    <section aria-labelledby="contact-title">
      <h1 id="contact-title">Contact</h1>
      <p>
        Vous avez un projet en tête ou souhaitez en savoir plus sur notre savoir-faire ? Nous sommes à votre écoute
        pour répondre à vos questions et vous accompagner dans la réalisation de vos envies en ferronnerie d’art,
        serrurerie et métallerie. Nous intervenons à Samoreau, Fontainebleau et dans les environs pour donner vie à vos
        projets.
      </p>
    </section>

    <section aria-labelledby="details-title">
      <h2 id="details-title">Détails de contact</h2>
      <address class="contact__details">
        <p>
          📍 <abbr title="Adresse de l'Atelier">Atelier</abbr> : 14 rue du Bois Gasseau, Samoreau, 77210
        </p>
        <p>
          📞 <abbr title="Numéro de Téléphone">Téléphone</abbr> :
          <a href="tel:0160716125" aria-label="Appeler le 01 60 71 61 25">01 60 71 61 25</a>
        </p>
        <p>
          📧 <abbr title="Adresse e-mail">Adresse e-mail</abbr> :
          <a href="mailto:ferronnerie.peltier@free.fr" aria-label="Envoyer un e-mail à ferronnerie.peltier@free.fr">
            ferronnerie.peltier@free.fr
          </a>
        </p>
        <p class="contact__details__hours">
          🕒 <abbr title="Horaires d'ouverture">Horaires</abbr> :
        </p>
        <ul>
          <li>Lundi au Vendredi : 8h - 12h / 13h - 16h</li>
          <li>Samedi : 9h - 12h</li>
          <li>Dimanche : Fermé</li>
        </ul>
      </address>
    </section>

    <section aria-labelledby="map-title">
      <h2 id="map-title">Carte</h2>
      <button v-if="isMapEnabled" @click="toggleMap" class="contact__btn" aria-label="Désactiver la carte">
        Désactiver la carte
      </button>
      <button v-if="!isMapEnabled" @click="toggleModal" class="contact__btn" aria-label="'Activer la carte'">
        Activer la carte
      </button>
      <iframe v-if="isMapEnabled" class="contact__map" title="Carte Google Maps de l'Atelier Peltier"
        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d5295.279079710308!2d2.7640807768856774!3d48.425064171276674!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x47e5f58d36811ea1%3A0x8947ea3a74ca0644!2sPeltier%20Willy!5e0!3m2!1sfr!2sfr!4v1743599900819!5m2!1sfr!2sfr"
        width="100%" height="100%" style="border:0;" allowfullscreen loading="lazy"
        referrerpolicy="no-referrer-when-downgrade">
      </iframe>
    </section>
    <ModalCustom :isOpen="isModalOpen" @close="toggleModal">
      <p class="contact__modal__title">
        Protection de votre vie privée
      </p>
      <p>
        Le site Ferronnerie Peltier respecte votre vie privée et ne collecte aucune donnée personnelle. Cependant, si
        vous choisissez d'activer la carte Google Maps, Google pourra collecter certaines informations, telles que votre
        adresse IP et votre position approximative, conformément à sa
        <a href="https://policies.google.com/privacy" target="_blank"
          aria-label='Politique de confidentialité de Google'>politique de confidentialité</a>.
        En activant la carte, vous consentez au traitement de ces données par Google.
      </p>
      <p>Vous pouvez activer ou désactiver la carte à tout moment.</p>
      <div class="contact__modal__btns">
        <button @click="acceptWarning" aria-label="Activer la carte" class="contact__btn">
          Activer
        </button>
        <button @click="toggleModal" aria-label="Annuler l'activation de la carte" class="contact__btn">
          Annuler
        </button>
      </div>
    </ModalCustom>
  </div>
</template>

<style lang="scss" scoped>
.contact {
  h1 {
    margin-top: 2rem;
  }

  section {
    padding: 0 10rem;

    @media screen and (max-width: 768px) {
      padding: 0 2rem;
    }
  }

  &__details {
    font-style: normal;

    &__hours {
      margin-bottom: 0;
    }

    ul {
      margin: 0;
    }
  }


  &__btn {
    display: inline-block;
    padding: 0.75rem 1.5rem;
    font-size: 1rem;
    font-weight: bold;
    color: var(--color-white);
    background-color: var(--color-primary);
    border: none;
    border-radius: 0.5rem;
    cursor: pointer;
    text-transform: uppercase;
    letter-spacing: 0.05em;
    transition: background-color 0.3s ease, transform 0.2s ease;

    &:hover {
      background-color: var(--color-secondary);
      transform: translateY(-2px);
    }

    &:active {
      transform: translateY(0);
    }

    &:focus {
      outline: 2px solid var(--color-secondary);
      outline-offset: 2px;
    }
  }

  &__map {
    height: 800px;
    margin: 2rem 0;
  }

  &__modal {
    &__title {
      font-size: 1.5rem;
      font-weight: bold;
      margin-bottom: 1rem;
    }

    &__btns {
      display: flex;
      justify-content: space-between;
      gap: 1rem;

      button {
        flex: 1;
      }
    }
  }
}
</style>
