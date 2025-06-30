<template>
  <div class="min-h-screen bg-white text-gray-900">
    <Header />
    <router-view />
  </div>
</template>

<script setup>
import Header from './components/Header.vue'
</script>