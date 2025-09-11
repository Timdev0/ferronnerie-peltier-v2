<script setup>
import { ref, onMounted, onUnmounted } from 'vue';
import ImageCard from '@/components/ImageCard.vue';
import img1 from '@/assets/imgs/01.jpg';
import img2 from '@/assets/imgs/02.jpg';
import img3 from '@/assets/imgs/03.jpg';
import img4 from '@/assets/imgs/17.jpg';
import img5 from '@/assets/imgs/05.jpg';
import imgThumb5 from '@/assets/imgs/05-thumb.jpg';
import img15 from '@/assets/imgs/15.jpg';
import imgThumb15 from '@/assets/imgs/15-thumb.jpg';
import img9 from '@/assets/imgs/09.jpg';
import imgThumb9 from '@/assets/imgs/09-thumb.jpg';
import img6 from '@/assets/imgs/06.jpg';
import imgThumb6 from '@/assets/imgs/06-thumb.jpg';
import img16 from '@/assets/imgs/16.jpg';
import imgThumb16 from '@/assets/imgs/16-thumb.jpg';
import img8 from '@/assets/imgs/08.jpg';
import imgThumb8 from '@/assets/imgs/08-thumb.jpg';

const isScrolled = ref(false);
const currentIndex = ref(0);
const images = [
  img1,
  img2,
  img3,
  img4,
];
let intervalId = null;

const handleScroll = () => {
  const scrollPosition = window.scrollY;
  isScrolled.value = scrollPosition > window.innerHeight * 0.5;
};

const startCarousel = () => {
  intervalId = setInterval(() => {
    currentIndex.value = (currentIndex.value + 1) % images.length;
  }, 4000);
};

const stopCarousel = () => {
  if (intervalId) clearInterval(intervalId);
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
  startCarousel();
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
  stopCarousel();
});

const imagesCreation = ref([
  {
    src: img5,
    thumb: imgThumb5,
    title: 'Main courante en fer forgé',
  },
  {
    src: img6,
    thumb: imgThumb6,
    title: 'Rampe d\'escalier en fer forgé',
  },
  {
    src: img15,
    thumb: imgThumb15,
    title: 'Portail en fer forgé',
  },
  {
    src: img9,
    thumb: imgThumb9,
    title: 'Décoration murale',
  },
  {
    src: img16,
    thumb: imgThumb16,
    title: 'Véranda en fer forgé',
  },
  {
    src: img8,
    thumb: imgThumb8,
    title: 'Serrurerie',
  },
]);

</script>


<template>
  <main class="home">
    <div class="carousel-container">
      <div class="carousel" :style="{ transform: `translateX(-${currentIndex * 100}%)` }">
        <div v-for="(image, index) in images" :key="index" class="carousel-slide"
          :style="{ backgroundImage: `url(${image})` }"></div>
      </div>
      <div class="carousel-text" :class="{ hidden: isScrolled }">
        <h1>Ferronnerie d'Art - Serrurerie - Métallerie | Peltier</h1>
        <p>Le feu et le fer au service de l'art</p>
      </div>
      <div class="scroll-indicator">
        <span>Défilez</span>
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="white" class="scroll-arrow">
          <path d="M12 16.5l-6-6h12l-6 6z" />
        </svg>
      </div>
    </div>
    <section class="intro">
      <div class="intro__left">
        <h2>Présentation</h2>
        <p>
          Créée en 1982, notre ferronnerie familiale, située à Samoreau près de Fontainebleau, est spécialisée dans la
          création et la fabrication de pièces en métal sur-mesure. Forts de plusieurs décennies d’expérience, nous
          concevons des ouvrages uniques tels que des portails, verrières, vérandas, escaliers, rampes débillardées,
          portes d’entrée, et bien d’autres éléments de serrurerie et de ferronnerie décorative.
        </p>

        <p>
          Transmise de père en fils, notre expertise artisanale allie savoir-faire traditionnel et techniques modernes
          pour répondre aux besoins spécifiques de nos clients. Chaque réalisation est pensée pour s'intégrer
          parfaitement à votre intérieur ou extérieur, en mettant en valeur l'esthétique et la durabilité du métal.
        </p>

        <p>
          N’hésitez pas à nous contacter pour discuter de votre projet ou demander un devis personnalisé. La Ferronnerie
          Peltier, c’est l’art du métal au service de vos envies !
        </p>
      </div>
      <div class="intro__right">
        <img src="/src/assets/imgs/peltier.jpg" alt="Ferronnerie Peltier Logo" class="intro__right__img" />
      </div>
    </section>
    <section class="creations">
      <h2>Nos Créations</h2>
      <p>Découvrez nos réalisations uniques, conçues sur-mesure pour sublimer vos espaces.</p>
      <div class="creations__grid">
        <ImageCard v-for="(image, index) in imagesCreation" :key="index" :src="image.src" :title="image.title"
          :thumb="image.thumb" />
      </div>
      <p>Pour voir plus de nos creations cliquez ici : <RouterLink class="gallery-link"
          aria-label="Accéder à la Galerie" to="/galerie">
          Accéder à la Galerie
        </RouterLink>
      </p>
    </section>
  </main>
</template>


<style scoped lang="scss">
.carousel-container {
  z-index: 1;
  position: relative;
  height: 100vh;
  top: -6rem;
  margin-bottom: -6rem;
  overflow: hidden;
  width: 100%;

  .carousel {
    display: flex;
    height: 100%;
    width: 100%;
    transition: transform 0.8s ease-in-out;
  }

  .carousel-slide {
    flex: 0 0 100%;
    height: 100%;
    background-size: cover;
    background-position: center;
  }

  .carousel-text {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    text-align: center;
    color: white;
    background-color: rgba(0, 0, 0, 0.7);
    padding: 1.5rem;
    border-radius: 8px;
    transition: opacity 0.3s ease, transform 0.3s ease;

    @media screen and (max-width: 768px) {
      left: 4%;
      transform: (translate(-2%, -50%));
    }

    &.hidden {
      opacity: 0;
      transform: translate(-50%, -100%);
    }

    h1 {
      font-family: 'Cinzel', serif;

      @media screen and (max-width: 768px) {
        font-size: 1.25rem;
      }
    }

    p {
      font-size: 1.2rem;
    }
  }
}

.scroll-indicator {
  position: absolute;
  bottom: 2rem;
  left: 50%;
  transform: translateX(-50%);
  text-align: center;
  color: var(--color-white);
  animation: bounce 1.5s infinite;

  span {
    font-size: 1rem;
    margin-bottom: 0.5rem;
    display: block;
    text-transform: uppercase;
    letter-spacing: 0.1em;
  }

  .scroll-arrow {
    width: 2rem;
    height: 2rem;
    fill: var(--color-white);
  }
}

section {
  padding: 2rem 10rem;

  @media screen and (max-width: 768px) {
    padding: 2rem;
  }
}

.intro {
  display: flex;
  flex-direction: row;
  gap: 2rem;

  @media screen and (max-width: 768px) {
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  &__left {
    @media screen and (min-width: 768px) {
      width: 70%;
    }
  }

  &__right {
    padding: 2rem;
    display: flex;
    justify-content: center;
    align-items: center;

    @media screen and (min-width: 768px) {
      padding: 0rem;
      width: 30%;
    }

    &__img {
      width: 100%;
      max-width: 350px;
    }
  }
}

.creations {
  text-align: center;
  background-color: var(--color-secondary);
  color: var(--color-white);

  &__grid {
    margin-top: 1.5rem;
    margin-bottom: 1.5rem;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 4rem;
    align-items: center;
  }

  p {
    font-size: 1.2rem;
    max-width: 800px;
    margin: 0 auto;
  }

  .gallery-link {
    color: var(--color-white);
  }

  .gallery-link:hover {
    color: var(--color-gold);
  }
}

@keyframes bounce {

  0%,
  100% {
    transform: translateX(-50%) translateY(0);
  }

  50% {
    transform: translateX(-50%) translateY(10px);
  }
}

@keyframes carousel-scroll {

  0%,
  33% {
    transform: translateX(0%);
  }

  34%,
  66% {
    transform: translateX(-100%);
  }

  67%,
  100% {
    transform: translateX(-200%);
  }
}
</style>
