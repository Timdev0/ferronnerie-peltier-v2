<template>
  <div>
    <div class="card">
      <img @click="imageShown = true" :src="thumb" :alt="`Image de ${title}`" />
      <p class="card__title">{{ title }}</p>
    </div>
    <div v-if="imageShown" @click="imageShown = false" class="card-full">
      <img @click.stop :src="src" :alt="`Image de ${title}`" class="card-full__img" />
      <button class="card-full__close-btn" @click="imageShown = false" aria-label="Fermer l'image">X</button>
    </div>
  </div>
</template>

<script setup>
import { ref, } from 'vue'
defineProps({
  title: String,
  thumb: String,
  src: String,
})

const imageShown = ref(false)

</script>

<style lang="scss" scoped>
.card {
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  cursor: pointer;
  max-width: 400px;
  height: auto;
  background-color: var(--color-white);
  padding: 0.5rem 0.5rem 0 0.5rem;
  color: var(--color-primary);
  border-radius: 0.5rem;

  &__title {
    margin-bottom: 0;
    padding: 0.5rem 0;
  }

  img {
    width: 100%;
    height: auto;
  }
}

.card-full {
  position: fixed;
  z-index: 2;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  background-color: rgba(0, 0, 0, 0.8);
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;

  img {
    cursor: default;
    max-width: 80%;
    max-height: 80%;
  }

  &__close-btn {
    position: absolute;
    top: 1rem;
    right: 1rem;
    background-color: transparent;
    color: var(--color-white);
    border: none;
    font-size: 1.5rem;
    cursor: pointer;
  }

  &__close-btn:hover {
    color: var(--color-gold)
  }
}
</style>
