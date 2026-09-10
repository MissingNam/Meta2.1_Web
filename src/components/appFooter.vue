<template>
    <v-footer color="blue-lighten-4" class="pa-4">
        <v-container>
            <v-row>
                <v-col cols="12" md="4">
                    <strong>Nombre:</strong> Jhared Leonardo Martinez Garcia
                </v-col>
                <v-col cols="12" md="4">
                    <strong>Matricula:</strong> 1197428
                </v-col>
                <v-col cols="12" md="4">
                    <strong>Fecha:</strong> {{ fechaActual }}
                </v-col>
            </v-row>
        </v-container>
    </v-footer>
</template>

<script setup>
const fechaActual = new Date().toLocaleDateString('es-MX')
</script>