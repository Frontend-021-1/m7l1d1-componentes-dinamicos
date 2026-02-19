<script setup>
import { ref, defineAsyncComponent, computed } from 'vue'
import ListLayout from '@/components/ListLayout.vue'
import TableLayout from '@/components/TableLayout.vue'
import CardLayout from './components/CardLayout.vue'

const layouts = {
  ListLayout,
  TableLayout,
  CardLayout
}

const componenteSeleccionado = ref('ListLayout')

const usuarios = ref([
  {
    id: 1,
    nombre: 'Juan',
    apellido: 'Perez',
    edad: 25,
    genero: 'Masculino',
    foto: 'https://randomuser.me/api/portraits/men/1.jpg',
  },
  {
    id: 2,
    nombre: 'Maria',
    apellido: 'Lopez',
    edad: 30,
    genero: 'Femenino',
    foto: 'https://randomuser.me/api/portraits/women/1.jpg',
  },
  {
    id: 3,
    nombre: 'Pedro',
    apellido: 'Garcia',
    edad: 35,
    genero: 'Masculino',
    foto: 'https://randomuser.me/api/portraits/men/2.jpg',
  },
  {
    id: 4,
    nombre: 'Ana',
    apellido: 'Martinez',
    edad: 40,
    genero: 'Femenino',
    foto: 'https://randomuser.me/api/portraits/women/2.jpg',
  },
  {
    id: 5,
    nombre: 'Luis',
    apellido: 'Garcia',
    edad: 45,
    genero: 'Masculino',
    foto: 'https://randomuser.me/api/portraits/men/3.jpg',
  },
  {
    id: 6,
    nombre: 'Ana',
    apellido: 'Martinez',
    edad: 50,
    genero: 'Femenino',
    foto: 'https://randomuser.me/api/portraits/women/3.jpg',
  },
])


</script>

<template>
  <main class="container my-5">
    <h1>Listado de usuarios</h1>

    <section class="border rounded-3 p-4">
      <h2>Elige cómo mostrarlos</h2>
      <ul class="nav nav-tabs">
        <li class="nav-item" v-for="(_, layout) in layouts">
          <a class="nav-link" href="#" @click="componenteSeleccionado = layout">{{
            layout }}</a>
        </li>

      </ul>
    </section>

    <section class="p-4 border rounded-3 my-4">
      <component :is="layouts[componenteSeleccionado]" :usuarios="usuarios" />
    </section>
  </main>
</template>

<style scoped></style>
