<template>
  <button :class="['btn', variantClass]" :aria-label="ariaLabel" @click="handleClick">
    <slot />
  </button>
</template>

<script setup>
import { defineProps, defineEmits, computed } from 'vue'

const props = defineProps({
  ariaLabel: {
    type: String,
    required: true,
  },
  variant: {
    type: String,
    default: 'primary',
  },
})

const emit = defineEmits(['click'])

const handleClick = (event) => {
  emit('click', event)
}

const variantClass = computed(() => {
  return `btn--${props.variant}`
})
</script>

<style scoped lang="scss">
.btn {
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

  &--secondary {
    background-color: var(--color-secondary);
    color: var(--color-white);

    &:hover {
      background-color: var(--color-primary);
    }
  }

  &--danger {
    background-color: var(--color-danger);
    color: var(--color-white);

    &:hover {
      background-color: var(--color-danger-dark);
    }
  }
}
</style>
