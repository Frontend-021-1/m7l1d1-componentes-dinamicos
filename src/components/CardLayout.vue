<script setup>
const props = defineProps({
  usuarios: {
    type: Array,
    required: true
  }
})
</script>

<template>
  <div class="card-group">
    <div class="card" v-for="usuario in usuarios" :key="usuario.id">
      <img :src="usuario.foto" class="card-img-top" :alt="`Imagen de ${usuario.nombre}`">
      <div class="card-body">
        <h5 class="card-title">{{ usuario.nombre }} {{ usuario.apellido }}</h5>
        <h6 class="card-subtitle">{{ usuario.genero }}</h6>
        <p class="card-text">Edad: {{ usuario.edad }} años</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
img {
  border-radius: 50%;
}
</style>