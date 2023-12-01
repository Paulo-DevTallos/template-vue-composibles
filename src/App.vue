<template>
  <div>
    <NavBar />
    <div class="flex justify-center mt-12 w-full">
      <RouterView />
    </div>
  </div>
</template>

<script setup>
import NavBar from '@/components/NavBar/index.vue';
</script>

<style scoped>
</style>
