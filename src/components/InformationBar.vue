<script setup>
import { defineProps } from 'vue'

const props = defineProps({
  marginTop: {
    type: String,
    default: '0px',
  },
  isScrolled: {
    type: Boolean,
    default: false
  }
})
</script>

<template>
  <section :class="['information-bar', { 'information-bar--scrolled': props.isScrolled }]"
    :style="{ 'margin-top': props.isScrolled ? '50px' : props.marginTop }">
    <p>
      La Ferronnerie Peltier est fermée pendant tout le mois d’août.
    </p>
  </section>
</template>

<style scoped lang="scss">
.information-bar {
  background-color: var(--color-danger);
  color: var(--color-white);
  text-align: center;
  padding: 0.75rem 0em;
  font-size: 0.95rem;
  line-height: 1.5;
  margin-top: 96px;
  height: auto;
  width: 100%;
  position: fixed;
  z-index: 8;

  &--scrolled {
    padding: 0.5rem 0em;
    font-size: 0.85rem;

    @media screen and (max-width: 768px) {
      margin-top: 34px !important;
    }

  }
}



.information-bar p {
  margin: 0;
}
</style>
