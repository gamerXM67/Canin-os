<script setup lang="ts">
import Index from '../components/Index.vue'
import Contact from '../components/Contact.vue'
import Navbar from '../components/Navbar.vue'
import { ref } from 'vue'
</script>

<template>
  <header>
    <Navbar />
  </header>
  <div class="layout">
    <Index />
  </div>
</template>

<style>
.layout {
  display: grid;
  grid-template-columns: 280px 1fr 340px;
  /* sidebar / contenu / colonne droite */
  height: 100vh;
  color: #333;
}
</style>
