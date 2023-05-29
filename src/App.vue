<script setup>
import Tarjeta from './components/Tarjeta.vue'
import bd from './services/bd';
</script>

<template>
  <header
    class="container d-flex justify-content-center align-items-center flex-column w-100 pt-4 gap-2"
  >
    <h1 class="fw-bold text-warning">We are committed expert partners</h1>
    <p>
      We place huge on strong relationships and have seen the benefit they bring to our business.
      Customer feedback is vital in helping us to get it right.
    </p>
  </header>
  
  <main class="container d-flex justify-content-center align-items-center flex-column gap-5 w-100 h-100 mt-4">
    <Tarjeta 
    v-for="(usuario, index) in bd"
    :key = "index"
    :nombre =usuario.nombre 
    :descripcion = usuario.descripcion 
    :img = usuario.img
    color="#222"
    />
  </main>
</template>

<style scoped></style>
