<script setup>
import { defineProps, defineEmits } from 'vue'

const props = defineProps({
  text: {
    type: String,
    default: 'Button'
  },
  disabled: {
    type: Boolean,
    default: false
  }
})

const emit = defineEmits(['click'])
</script>

<template>
  <button
      class="btn-primary"
      @click="emit('click')"
      :disabled="disabled"
  >
    {{ text }}
  </button>
</template>

<style scoped>
  .btn-primary {
    padding: 12px 32px;
    border-radius: 999px;
    border: none;
    background-color: var(--content-dark);
    color: var(--content-light);
    cursor: pointer;
    transition: background-color 0.3s;
  }

  .btn-primary:disabled {
    background-color: var(--content-darker);
    color: var(--content-neutral);
    cursor: not-allowed;
  }

  @media screen and (max-width: 460px) {
    .btn-primary {
      width: 100%;
      max-width: 327px;
    }
  }
</style>