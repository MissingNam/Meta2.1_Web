<template>
  <v-app>
    <appHeader />
    <v-main>
      <v-container>
        <v-row justify="center">
          <v-col cols="12" md="5">
            <TarjetaImagen
              :imagenUrl="imagen1.url"
              titulo="Imagen 1"
              descripcion="Imagen Sacada de picsum"
              :autor="imagen1.autor"
              />
          </v-col>
          <v-col cols="12" md="5">
            <TarjetaImagen
              :imagenUrl="imagen2.url"
              titulo="Imagen 2"
              descripcion="Otra imagen sacada de picsum"
              :autor="imagen2.autor"
              />
          </v-col>
        </v-row>

        <v-row justify="center" class="my-4">
          <v-btn color="primary" :loading="cargando" :disabled="cargando" @click="actualizarImagenes">
            Actualizar imágenes
          </v-btn>
        </v-row>

        <v-row v-if="error">
          <v-col>
            <v-alert type="error">{{ error }}</v-alert>
          </v-col>
        </v-row>

        <v-row>
          <v-col cols="12">
            <tablaDatos />
          </v-col>
        </v-row>

      </v-container>
    </v-main>

    <appFooter />
  </v-app>
</template>

<script setup>
import {ref, onMounted} from 'vue';
import appHeader from './components/appHeader.vue'
import appFooter from './components/appFooter.vue'
import TarjetaImagen from './components/tarjetaImagen.vue'
import tablaDatos from './components/tablaDatos.vue'

const imagen1 = ref({ url: '', autor: '' })
const imagen2 = ref({ url: '', autor: '' })
const cargando = ref(false)
const error = ref(null)

async function actualizarImagenes() {
  cargando.value = true
  error.value = null

  try {
    const respuesta = await fetch('https://picsum.photos/v2/list?page=1&limit=50')
    if (!respuesta.ok) throw new Error('No se pudo conectar con la API')

    const lista = await respuesta.json()
    console.log(lista);

    // Elegir dos índices aleatorios distintos
    const idx1 = Math.floor(Math.random() * lista.length)
    let idx2 = Math.floor(Math.random() * lista.length)
    while (idx2 === idx1) {
      idx2 = Math.floor(Math.random() * lista.length)
    }

    const foto1 = lista[idx1]
    const foto2 = lista[idx2]

    imagen1.value = {
      url: foto1.download_url,
      autor: foto1.author
    }
    imagen2.value = {
      url: foto2.download_url,
      autor: foto2.author
    }
  } catch (e) {
    error.value = 'Ocurrió un error al cargar las imágenes. Intenta de nuevo.'
  } finally {
    cargando.value = false
  }
}

onMounted(() => {
  actualizarImagenes()
})
</script>
