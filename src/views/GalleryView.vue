<script setup>
import { ref } from 'vue'
import ImageCard from '@/components/ImageCard.vue';
import img05 from '@/assets/imgs/05.jpg'
import img05Thumb from '@/assets/imgs/05-thumb.jpg'
import img06 from '@/assets/imgs/06.jpg'
import img06Thumb from '@/assets/imgs/06-thumb.jpg'
import img07 from '@/assets/imgs/07.jpg'
import img07Thumb from '@/assets/imgs/07-thumb.jpg'
import img08 from '@/assets/imgs/08.jpg'
import img08Thumb from '@/assets/imgs/08-thumb.jpg'
import img09 from '@/assets/imgs/09.jpg'
import img09Thumb from '@/assets/imgs/09-thumb.jpg'
import img10 from '@/assets/imgs/10.jpg'
import img10Thumb from '@/assets/imgs/10-thumb.jpg'
import img11 from '@/assets/imgs/11.jpg'
import img11Thumb from '@/assets/imgs/11-thumb.jpg'
import img12 from '@/assets/imgs/12.jpg'
import img12Thumb from '@/assets/imgs/12-thumb.jpg'
import img13 from '@/assets/imgs/13.jpg'
import img13Thumb from '@/assets/imgs/13-thumb.jpg'
import img14 from '@/assets/imgs/14.jpg'
import img14Thumb from '@/assets/imgs/14-thumb.jpg'
import img15 from '@/assets/imgs/15.jpg'
import img15Thumb from '@/assets/imgs/15-thumb.jpg'
import img16 from '@/assets/imgs/16.jpg'
import img16Thumb from '@/assets/imgs/16-thumb.jpg'
import img17 from '@/assets/imgs/17.jpg'
import img17Thumb from '@/assets/imgs/17-thumb.jpg'
import img18 from '@/assets/imgs/18.jpg'
import img18Thumb from '@/assets/imgs/18-thumb.jpg'
import img19 from '@/assets/imgs/19.jpg'
import img19Thumb from '@/assets/imgs/19-thumb.jpg'
import img20 from '@/assets/imgs/20.jpg'
import img20Thumb from '@/assets/imgs/20-thumb.jpg'
import img91 from '@/assets/imgs/91.jpg'
import img91Thumb from '@/assets/imgs/91-thumb.jpg'
import img92 from '@/assets/imgs/92.jpg'
import img92Thumb from '@/assets/imgs/92-thumb.jpg'
import img93 from '@/assets/imgs/93.jpg'
import img93Thumb from '@/assets/imgs/93-thumb.jpg'
import img94 from '@/assets/imgs/94.jpg'
import img94Thumb from '@/assets/imgs/94-thumb.jpg'
import img95 from '@/assets/imgs/95.jpg'
import img95Thumb from '@/assets/imgs/95-thumb.jpg'
import img96 from '@/assets/imgs/96.jpg'
import img96Thumb from '@/assets/imgs/96-thumb.jpg'
import img97 from '@/assets/imgs/97.jpg'
import img97Thumb from '@/assets/imgs/97-thumb.jpg'
import img98 from '@/assets/imgs/98.jpg'
import img98Thumb from '@/assets/imgs/98-thumb.jpg'
import img99Thumb from '@/assets/imgs/99-thumb.jpg'

const imagesGallery = ref([
  { src: img05, thumb: img05Thumb, title: 'Main courante en fer forgé' },
  { src: img06, thumb: img06Thumb, title: 'Rampe d\'escalier' },
  { src: img07, thumb: img07Thumb, title: 'Portail en fer forgé' },
  { src: img08, thumb: img08Thumb, title: 'Serrurerie' },
  { src: img09, thumb: img09Thumb, title: 'Décoration murale' },
  { src: img10, thumb: img10Thumb, title: 'Garde-corps en fer forgé' },
  { src: img11, thumb: img11Thumb, title: 'Véranda' },
  { src: img12, thumb: img12Thumb, title: 'Meuble' },
  { src: img13, thumb: img13Thumb, title: 'Verrière' },
  { src: img14, thumb: img14Thumb, title: 'Marquise en fer forgé' },
  { src: img15, thumb: img15Thumb, title: 'Portail en fer forgé' },
  { src: img16, thumb: img16Thumb, title: 'Véranda en fer forgé' },
  { src: img17, thumb: img17Thumb, title: 'Marquise' },
  { src: img18, thumb: img18Thumb, title: 'Véranda' },
  { src: img19, thumb: img19Thumb, title: 'Portail' },
  { src: img20, thumb: img20Thumb, title: 'Table en fer forgé' },
])

const imagesGalleryVertical = ref([
  { src: img91, thumb: img91Thumb, title: 'Portail décoratif en fer forgé' },
  { src: img92, thumb: img92Thumb, title: 'Meuble' },
  { src: img93, thumb: img93Thumb, title: 'Escalier en fer forgé' },
  { src: img94, thumb: img94Thumb, title: 'Grille de sécurité en fer forgé' },
  { src: img95, thumb: img95Thumb, title: 'Rampes / Main courante d\'escalier' },
  { src: img96, thumb: img96Thumb, title: 'Porte coulissante' },
  { src: img97, thumb: img97Thumb, title: 'Grille décorative' },
  { src: img98, thumb: img98Thumb, title: 'Décoration murale' },
  { src: img99Thumb, thumb: img99Thumb, title: 'Rampes / Main courante d\'escalier' },
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
      <hr>
      <div class="gallery__grid">
        <ImageCard v-for="(image, index) in imagesGalleryVertical" :key="index" :src="image.src" :title="image.title"
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

  hr {
    opacity: 0.5;
  }

  &__grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 2rem;
    margin-top: 2rem;
    margin-bottom: 2rem;

    @media screen and (max-width: 768px) {
      gap: 1rem;
      margin-top: 1rem;
    }
  }
}
</style>
