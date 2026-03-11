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
    <Avis />
    <Faq />
    <Contact />
  </main>
  <footer>

  </footer>
</template>

<style>
main {
  scroll-behavior: smooth;
}
</style>
