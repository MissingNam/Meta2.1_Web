<template>
  <v-table>
    <thead>
      <tr>
        <th>Habilidad</th>
        <th>Nivel</th>
        <th>Años de experiencia</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="item in habilidades" :key="item.nombre">
        <td>{{ item.nombre }}</td>
        <td>{{ item.nivel }}</td>
        <td>{{ item.anios }}</td>
      </tr>
    </tbody>
  </v-table>
</template>

<script setup>
const habilidades = [
  { nombre: 'Vue.js', nivel: 'Intermedio', anios: 1 },
  { nombre: 'JavaScript', nivel: 'Intermedio', anios: 2 },
  { nombre: 'HTML/CSS', nivel: 'Avanzado', anios: 2 },
  { nombre: 'Git', nivel: 'Básico', anios: 1 },
]
</script>