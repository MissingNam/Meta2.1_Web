# Mi Portafolio Fotográfico

Aplicación Vue 3 + Vuetify 3 que consume la API de Picsum para mostrar imágenes aleatorias.

## Captura de pantalla
![screenshot](Screenshoot.png)

## Tecnologías
- Vue 3 (Composition API)
- Vuetify 3
- Vite
- Picsum API

## Instalación
\`\`\`bash
pnpm install <br>
pnpm run dev
\`\`\`

## Estructura del proyecto
proyecto-vue-vuetify/<br>
│<br>
├── public/<br>
│   └── favicon.ico                # Ícono de la pestaña del navegador<br>
│<br>
├── src/<br>
│   ├── assets/
│   │   └── logo.png               # Imágenes locales (si usas alguna, opcional)<br>
│   │<br>
│   ├── components/<br>
│   │   ├── AppHeader.vue          # Barra superior (v-app-bar)<br>
│   │   ├── AppFooter.vue          # Pie de página (v-footer)<br>
│   │   ├── TarjetaConImagen.vue   # Tarjeta reutilizable con props<br>
│   │   └── TablaDeDatos.vue       # Tabla de habilidades (v-table)<br>
│   │<br>
│   ├── services/<br>
│   │   └── picsumApi.js           # (Opcional pero recomendado) centraliza el fetch<br>
│   │<br>
│   ├── plugins/<br>
│   │   └── vuetify.js             # Configuración/registro de Vuetify<br>
│   │<br>
│   ├── App.vue                    # Layout raíz: Header + main + Footer<br>
│   └── main.js                    # Punto de entrada: monta la app Vue<br>
│<br>
├── index.html                     # HTML base donde Vue se "inyecta"<br>
├── package.json                   # Dependencias y scripts (pnpm run dev, etc.)<br>
├── .gitignore<br>
└── README.md<br>