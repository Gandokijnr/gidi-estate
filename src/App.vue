<script setup>
import { RouterView } from 'vue-router'
import Navbar from '@/components/Navbar/NavbarComponent.vue'
import FooterSection from '@/components/FooterSection/FooterComponent.vue'
</script>

<template>
  <Navbar />
  <RouterView />
  <FooterSection />
</template>

<style scoped></style>
