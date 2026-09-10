<template>
    <v-card>
        <v-img :src="imagenUrl" heigth="200" cover></v-img>
        <v-card-title>{{ titulo }}</v-card-title>
        <v-card-subtitle>Foto por: {{ autor }}</v-card-subtitle>
        <v-card-text>{{ descripcion }}</v-card-text>
    </v-card>
</template>

<script setup>
defineProps({
    imagenUrl: { type: String, required: true },
    titulo: { type: String, default: 'Sin título' },
    descripcion: { type: String, default: '' },
    autor: { type: String, default: 'Desconocido' }
})
</script>