<template>
  <div>
    <NavBar :shop="navBarShop" :primary="navBarPrimary" :logged="navBarLogged" class="sticky top-0 z-50"></NavBar>
    <NuxtPage />
    <Footer />
  </div>
</template>

<script setup>
import { ref, watch, provide } from 'vue'
import { useRoute } from 'vue-router'

const navBarPrimary = ref('')
const navBarLogged = ref(false)
const navBarShop = ref(false)

const itemsInCart = ref([])
const arrayJuegos = ref([
  {
    img: '/arrayJuegos/1.jpg',
    name: 'Contra 1'
  }
])

async function fetchGames() {
  const url = 'https://api.rawg.io/api/games?key=ffaa0b8dcb864e25b3011838b3ea1536&dates=2019-09-01,2019-09-30&platforms=18,1,7'
  
  try {
    const response = await fetch(url)
    console.log('Estado de la respuesta:', response.status) // Estado de la respuesta
    console.log('Respuesta completa:', response) // Respuesta completa

    if (!response.ok) {
      throw new Error(`Error en la respuesta de la API: ${response.statusText}`)
    }

    const data = await response.json()
    console.log('Datos de la API:', data) // Datos recibidos de la API

    if (data.results && data.results.length > 0) {
      for (const game of data.results) {
        console.log('Juego recibido:', game) // Datos del juego individual
        if (game.name && game.background_image) {
          arrayJuegos.value.push({
            img: game.background_image,
            name: game.name
          })
        }
      }
    } else {
      console.warn('No se encontraron juegos en la respuesta de la API')
    }

  } catch (error) {
    console.error('Error al hacer el fetch a la API:', error)
  }
}

fetchGames()

provide('itemsInCart', itemsInCart)
provide('arrayJuegos', arrayJuegos)
provide('navBarLogged', navBarLogged)

const route = useRoute()

watch(route, (newRoute) => {
  if (newRoute.path.includes('tiendaJuegos')) {
    navBarShop.value = true
    navBarPrimary.value = 'juegos'
  } else if (newRoute.path.includes('tiendaGeneros')) {
    navBarShop.value = true
    navBarPrimary.value = 'juegos'
  } else if (newRoute.path.includes('tiendaNuevos')) {
    navBarShop.value = true
    navBarPrimary.value = 'nuevos'
  } else if (newRoute.path.includes('tiendaOfertas')) {
    navBarShop.value = true
    navBarPrimary.value = 'ofertas'
  } else if (newRoute.path.includes('tiendaPuntos')) {
    navBarPrimary.value = 'puntos'
    navBarShop.value = true
  } else {
    navBarPrimary.value = ''
    navBarShop.value = false
  }
}, { immediate: true })

</script>



<style lang="sass">

</style>