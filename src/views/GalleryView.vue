<script setup>
import { ref } from 'vue'
import ImageCard from '@/components/ImageCard.vue';

const imagesGallery = ref([
  {
    src: '/src/assets/imgs/05.jpg',
    thumb: '/src/assets/imgs/05-thumb.jpg',
    title: 'Main courante en fer forgé',
  },
  {
    src: '/src/assets/imgs/06.jpg',
    thumb: '/src/assets/imgs/06-thumb.jpg',
    title: 'Rampe d\'escalier',
  },
  {
    src: '/src/assets/imgs/07.jpg',
    thumb: '/src/assets/imgs/07-thumb.jpg',
    title: 'Portail en fer forgé',
  },
  {
    src: '/src/assets/imgs/08.jpg',
    thumb: '/src/assets/imgs/08-thumb.jpg',
    title: 'Serrurerie',
  },
  {
    src: '/src/assets/imgs/09.jpg',
    thumb: '/src/assets/imgs/09-thumb.jpg',
    title: 'Décoration murale',
  },
  {
    src: '/src/assets/imgs/10.jpg',
    thumb: '/src/assets/imgs/10-thumb.jpg',
    title: 'Garde-corps en fer forgé',
  },
  {
    src: '/src/assets/imgs/11.jpg',
    thumb: '/src/assets/imgs/11-thumb.jpg',
    title: 'Véranda',
  },
  {
    src: '/src/assets/imgs/12.jpg',
    thumb: '/src/assets/imgs/12-thumb.jpg',
    title: 'Meuble',
  },
  {
    src: '/src/assets/imgs/13.jpg',
    thumb: '/src/assets/imgs/13-thumb.jpg',
    title: 'Verrière',
  },
  {
    src: '/src/assets/imgs/14.jpg',
    thumb: '/src/assets/imgs/14-thumb.jpg',
    title: 'Marquise en fer forgé',
  },
  {
    src: '/src/assets/imgs/15.jpg',
    thumb: '/src/assets/imgs/15-thumb.jpg',
    title: 'Portail en fer forgé',
  },
  {
    src: '/src/assets/imgs/16.jpg',
    thumb: '/src/assets/imgs/16-thumb.jpg',
    title: 'Véranda en fer forgé',
  },
  {
    src: '/src/assets/imgs/17.jpg',
    thumb: '/src/assets/imgs/17-thumb.jpg',
    title: 'Marquise',
  },
  {
    src: '/src/assets/imgs/18.jpg',
    thumb: '/src/assets/imgs/18-thumb.jpg',
    title: 'Véranda',
  },
  {
    src: '/src/assets/imgs/19.jpg',
    thumb: '/src/assets/imgs/19-thumb.jpg',
    title: 'Portail',
  },
  {
    src: '/src/assets/imgs/20.jpg',
    thumb: '/src/assets/imgs/20-thumb.jpg',
    title: 'Table en fer forgé',
  },
  {
    src: '/src/assets/imgs/91.jpg',
    thumb: '/src/assets/imgs/91-thumb.jpg',
    title: 'Portail décoratif en fer forgé',
  },
  {
    src: '/src/assets/imgs/92.jpg',
    thumb: '/src/assets/imgs/92-thumb.jpg',
    title: 'Meuble',
  },
  {
    src: '/src/assets/imgs/93.jpg',
    thumb: '/src/assets/imgs/93-thumb.jpg',
    title: 'Escalier en fer forgé',
  },
  {
    src: '/src/assets/imgs/94.jpg',
    thumb: '/src/assets/imgs/94-thumb.jpg',
    title: 'Grille de sécurité en fer forgé',
  },
  {
    src: '/src/assets/imgs/95.jpg',
    thumb: '/src/assets/imgs/95-thumb.jpg',
    title: 'Rampes / Main courante d\'escalier',
  },
  {
    src: '/src/assets/imgs/96.jpg',
    thumb: '/src/assets/imgs/96-thumb.jpg',
    title: 'Porte coulissante',
  },
  {
    src: '/src/assets/imgs/97.jpg',
    thumb: '/src/assets/imgs/97-thumb.jpg',
    title: 'Grille décorative',
  },
  {
    src: '/src/assets/imgs/98.jpg',
    thumb: '/src/assets/imgs/98-thumb.jpg',
    title: 'Décoration murale',
  },
  {
    src: '/src/assets/imgs/99-thumb.jpg',
    thumb: '/src/assets/imgs/99-thumb.jpg',
    title: 'Rampes / Main courante d\'escalier',
  },
])
</script>

<template>
  <div class="gallery">
    <section aria-labelledby="gallery-title">
      <h1 id="gallery-title">Galerie</h1>
      <p>
        Plongez au cœur de notre savoir-faire artisanal à travers cette galerie de créations uniques. Chaque pièce
        présentée ici témoigne de notre passion pour la ferronnerie d'art.
        Que ce soit des portails élégants, des rampes d’escaliers sur-mesure ou encore des verrières raffinées, chaque
        ouvrage est conçu avec précision et souci du détail.
        Laissez-vous inspirer par nos réalisations et imaginez votre propre projet sur-mesure.
      </p>
      <div class="gallery__grid">
        <ImageCard v-for="(image, index) in imagesGallery" :key="index" :src="image.src" :title="image.title"
          :thumb="image.thumb" />
      </div>
    </section>
  </div>
</template>

<style lang="scss" scoped>
.gallery {
  section {
    padding: 2rem 10rem;

    @media screen and (max-width: 768px) {
      padding: 2rem;
    }
  }

  &__grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 2rem;
    margin-top: 2rem;

    @media screen and (max-width: 768px) {
      gap: 1rem;
      margin-top: 1rem;
    }
  }
}
</style>
