<script setup>
const props = defineProps({
  usuarios: {
    type: Array,
    required: true
  }
})
</script>

<template>
  <table class="table">
    <thead>
      <tr>
        <th scope="col">#</th>
        <th scope="col">Nombre</th>
        <th scope="col">Apellido</th>
        <th scope="col">Edad</th>
        <th scope="col">Género</th>
        <th scope="col">Foto</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(usuario, index) in usuarios" :key="usuario.id">
        <th scope="row">{{ index + 1 }}</th>
        <td>{{ usuario.nombre }}</td>
        <td>{{ usuario.apellido }}</td>
        <td>{{ usuario.edad }}</td>
        <td>{{ usuario.genero }}</td>
        <td><img :src="usuario.foto" :alt="`Imagen de ${usuario.nombre}`"></td>
      </tr>

    </tbody>
  </table>
</template>

<style scoped></style>