<script setup lang="ts">
import { ref } from 'vue'
import DesktopNavbar from './components/DesktopNavbar.vue'

const isMenuOpen = ref(false)
</script>

<template>
  <DesktopNavbar v-model:isMenuOpen="isMenuOpen" />
  <router-view />
</template>

<style scoped>

</style>
