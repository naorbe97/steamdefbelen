<template>
  <div class="flex flex-col bg-white">
    <div class="flex justify-between px-12 py-6 items-center">
      <NuxtLink to="/"><img src="/steamLogo.svg" alt="logo" /></NuxtLink>
      <div class="flex gap-12 h-fit items-center">
        <NuxtLink to="/tiendaNuevos">
          <Button
            :littleText="true"
            :class="['button', { 'button-gray': hoverButton === 'nuevos' && primary !== 'nuevos' }]"
            :style="{ backgroundColor: primary === 'nuevos' || primary === 'tienda' ? 'rgb(0 255 3 / var(--tw-bg-opacity))' : 'transparent' }"
            @click="changePrimary('nuevos')"
            @mouseover="hoverButton = 'nuevos'"
            @mouseleave="hoverButton = ''">Tienda
          </Button>
        </NuxtLink>
        <Button
          :littleText="true"
          :class="['button', { 'button-gray': hoverButton === 'comunidad' && primary !== 'comunidad' }]"
          :style="{ backgroundColor: primary === 'comunidad' ? 'rgb(0 255 3 / var(--tw-bg-opacity))' : 'transparent' }"
          @click="changePrimary('comunidad')"
          @mouseover="hoverButton = 'comunidad'"
          @mouseleave="hoverButton = ''">Comunidad
        </Button>
        <Button
          :littleText="true"
          :class="['button', { 'button-gray': hoverButton === 'soporte' && primary !== 'soporte' }]"
          :style="{ backgroundColor: primary === 'soporte' ? 'rgb(0 255 3 / var(--tw-bg-opacity))' : 'transparent' }"
          @click="changePrimary('soporte')"
          @mouseover="hoverButton = 'soporte'"
          @mouseleave="hoverButton = ''"
>Soporte
        </Button>
        <Button :icon="'community'" :littleIcon="true"></Button>
        <Button :littleText="true" :color="'gray'">Instala Steam</Button>
        <template v-if="!logged">
          <NuxtLink to="/inicio">
            <Button :littleText="true" :color="'primary'">Inicia Sesión</Button>
          </NuxtLink>
        </template>
        <template v-else>
          <img src="/user.png" alt="" class="w-14">
        </template>
      </div>
    </div>
    <div v-if="shop" class="flex flex-col gap-7 p-12">
      <div class="flex justify-between">
        <h2>Tienda</h2>
        <div class="flex gap-6">
          <Button :icon="'community'"></Button>
          <div class="flex relative">
            <NuxtLink to="/shoppingCart">
              <Button :icon="'cart'"></Button>
            </NuxtLink>
            <p v-if="itemsInCart.length > 0" class="flex justify-center items-center text-black bg-primary w-5 h-5 mono rounded-full absolute top-0 left-8">
              {{ itemsInCart.length }}
            </p>
          </div>
        </div>
      </div>
      <div class="flex gap-11">
        <NuxtLink v-if="primary === 'nuevos'" to="/tiendaNuevos" @click="changePrimary('')">
          <Button
            :littleText="true"
            :class="['button', { 'button-gray': hoverButton === 'nuevos' && primary !== 'nuevos' }]"
            :style="{ backgroundColor: primary === 'nuevos' ? 'rgb(0 255 3 / var(--tw-bg-opacity))' : 'transparent' }"
            @mouseover="hoverButton = 'nuevos'"
            @mouseleave="hoverButton = ''"
          >
            Nuevos y Destacables
          </Button>
        </NuxtLink>
        <NuxtLink v-else to="/tiendaNuevos" @click="changePrimary('nuevos')" @mouseover="hoverButton = 'nuevos'" @mouseleave="hoverButton = ''">
          <Button :littleText="true" :class="['button', { 'button-gray': hoverButton === 'nuevos' && primary !== 'nuevos' }]">
            Nuevos y Destacables
          </Button>
        </NuxtLink>
        <NuxtLink v-if="primary === 'juegos'" to="/tiendaGeneros" @click="changePrimary('')">
          <Button
            :littleText="true"
            :class="['button', { 'button-gray': hoverButton === 'juegos' && primary !== 'juegos' }]"
            :style="{ backgroundColor: primary === 'juegos' ? 'rgb(0 255 3 / var(--tw-bg-opacity))' : 'transparent' }"
            @mouseover="hoverButton = 'juegos'"
            @mouseleave="hoverButton = ''"
          >
            Juegos por tipo
          </Button>
        </NuxtLink>
        <NuxtLink v-else to="/tiendaGeneros" @click="changePrimary('juegos')" @mouseover="hoverButton = 'juegos'" @mouseleave="hoverButton = ''">
          <Button :littleText="true" :class="['button', { 'button-gray': hoverButton === 'juegos' && primary !== 'juegos' }]">
            Juegos por tipo
          </Button>
        </NuxtLink>
        <NuxtLink v-if="primary === 'ofertas'" to="/tiendaOfertas" @click="changePrimary('')">
          <Button
            :littleText="true"
            :class="['button', { 'button-gray': hoverButton === 'ofertas' && primary !== 'ofertas' }]"
            :style="{ backgroundColor: primary === 'ofertas' ? 'rgb(0 255 3 / var(--tw-bg-opacity))' : 'transparent' }"
            @mouseover="hoverButton = 'ofertas'"
            @mouseleave="hoverButton = ''"
          >
            Ofertas
          </Button>
        </NuxtLink>
        <NuxtLink v-else to="/tiendaOfertas" @click="changePrimary('ofertas')" @mouseover="hoverButton = 'ofertas'" @mouseleave="hoverButton = ''">
          <Button :littleText="true" :class="['button', { 'button-gray': hoverButton === 'ofertas' && primary !== 'ofertas' }]">
            Ofertas
          </Button>
        </NuxtLink>
        <NuxtLink v-if="primary === 'puntos'" to="/tiendaPuntos" @click="changePrimary('')">
          <Button
            :littleText="true"
            :class="['button', { 'button-gray': hoverButton === 'puntos' && primary !== 'puntos' }]"
            :style="{ backgroundColor: primary === 'puntos' ? 'rgb(0 255 3 / var(--tw-bg-opacity))' : 'transparent' }"
            @mouseover="hoverButton = 'puntos'"
            @mouseleave="hoverButton = ''"
          >
            Tienda por puntos
          </Button>
        </NuxtLink>
        <NuxtLink v-else to="/tiendaPuntos" @click="changePrimary('puntos')" @mouseover="hoverButton = 'puntos'" @mouseleave="hoverButton = ''">
          <Button :littleText="true" :class="['button', { 'button-gray': hoverButton === 'puntos' && primary !== 'puntos' }]" :style="{ backgroundColor: primary === 'puntos' ? 'rgb(0 255 3 / var(--tw-bg-opacity))' : 'transparent' }">
            Tienda por puntos
          </Button>
        </NuxtLink>
      </div>
    </div>
  </div>
</template>

<script setup>
import { defineProps, ref } from 'vue';
import { inject } from 'vue';
import Button from "./mockComponents/Button.vue";

const itemsInCart = inject('itemsInCart');
const props = defineProps({
  shop: Boolean,
  primary: String,
  logged: Boolean
});

const hoverButton = ref('');

const changePrimary = (value) => {
  props.primary = value;
  hoverButton.value = ''; // Reset hover when a button is clicked
};
</script>
