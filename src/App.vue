<script setup lang="ts">
import Navbar from '../components/Navbar.vue'
import Index from '../components/Index.vue'
import Presentation from '../components/Presentation.vue'
import Services from '../components/Services.vue'
import Tarifs from '../components/Tarifs.vue'
import Galerie from '../components/Galerie.vue'
import Avis from '../components/Avis.vue'
import Faq from '../components/Faq.vue'
import Contact from '../components/Contact.vue'
import { ref } from 'vue'
</script>

<template>
  <header>
    <Navbar />
  </header>
  <main>
    <Index />
    <Presentation />
    <Services />
    <Tarifs />
    <Galerie />
    <!-- <Avis /> -->
    <Faq />
    <Contact />
  </main>
  <footer>

  </footer>
</template>

<style>
html {
  scroll-behavior: smooth;
}

body {
  margin: 0;
  padding: 0;
  background: #ffffff;
  background: radial-gradient(circle, rgba(255, 255, 255, 1) 0%, rgba(224, 238, 255, 1) 100%);
  font-family: 'Nunito', sans-serif;
}
</style>
