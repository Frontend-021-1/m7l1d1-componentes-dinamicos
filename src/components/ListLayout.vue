<script setup>
const props = defineProps({
  usuarios: {
    type: Array,
    required: true
  }
})
</script>

<template>
  <div>
    <h3>Lista de usuarios</h3>

    <ul class="list-group">
      <li class="list-group-item" v-for="usuario in usuarios" :key="usuario.id">{{ usuario.nombre }} {{ usuario.apellido
      }} - {{ usuario.edad }} años - {{ usuario.genero }}</li>
    </ul>

  </div>
</template>

<style scoped></style>