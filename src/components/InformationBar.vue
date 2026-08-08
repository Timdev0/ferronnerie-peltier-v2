<script setup>

const props = defineProps({
  isActive: {
    type: Boolean,
    default: false
  }
})

</script>

<template>
  <section class="information-bar" :class="{ 'information-bar--disabled': !isActive }">
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
  padding: 0.75rem 0;
  line-height: 1.5;
  height: auto;
  width: 100%;

  @media screen and (max-width: 768px) {
    padding: 0.5rem 0;
  }

  &--disabled {
    display: none;
  }
}

.information-bar p {
  margin: 0;
}
</style>
