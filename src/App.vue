<script setup lang="ts">
  import { ref, onMounted, onUnmounted } from 'vue'

  const width = ref(window.innerWidth)
  const height = ref(window.innerHeight)

  function updateSize() {
    width.value = window.innerWidth
    height.value = window.innerHeight
  }

  onMounted(() => {
    window.addEventListener('resize', updateSize)
  })

  onUnmounted(() => {
    window.removeEventListener('resize', updateSize)
  })
</script>

<template>
  <div>
    <router-link to="/login">login</router-link>
    <router-link to="/profile">profile</router-link>
    <div>
      <p>Ширина экрана: {{width}}px</p>
      <p>Высота экрана: {{height}}px</p>
    </div>
  </div>
  <router-view/>
</template>

<style scoped>

</style>
