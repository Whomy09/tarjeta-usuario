<template>
  <article class="d-flex p-2 gap-2 rounded-2 w-50" :style="backgroundColor">
    <div class="d-flex justify-content-center align-items-center w-25">
      <img :src="props.img" alt="foto-de-perfil" class="rounded-circle" width="120" height="120"/>
    </div>
    <div class="d-flex flex-column w-75">
      <p class="text-white fs-6">
        "{{ props.descripcion }}"
      </p>
      <span class="fw-bold text-white">{{ props.nombre }}</span>
    </div>
  </article>
</template>

<script lang="ts" setup>
import { ref } from 'vue';
import { onUpdated } from 'vue';

const props = defineProps({
  img: String,
  nombre: String,
  descripcion: String,
  color: String
});

let descripcion = ref(props.descripcion)
let nombre = ref(props.nombre);
let img = ref(props.img);
let backgroundColor = ref(`background-color:${props.color}`);

onUpdated(() => {
  nombre.value = props.nombre;
  descripcion.value = props.descripcion;
  img.value = props.img;
  backgroundColor.value = `background-color:${props.color}`
})
</script>

<style scoped>
</style>
