<template>
  <div class="flex flex-col bg-g200 gap-24 p-14">
    <div class="flex justify-between">
      <p class="text-primary">
        Para cualquier pregunta, por favor, contacta con steam@support.com
      </p>
      <div class="flex gap-6">
        <div class="flex flex-col gap-3">
          <h5>Tienda</h5>
          <NuxtLink to="/tiendaNuevos"><p>Nuevos y destacables</p></NuxtLink>
          <NuxtLink to="/tiendaJuegos"><p>Juegos por tipo</p></NuxtLink>
          <NuxtLink to="/tiendaOfertas"><p>Ofertas</p></NuxtLink>
          <NuxtLink to="/tiendaPuntos"><p>Tienda de puntos</p></NuxtLink>
        </div>
        <div class="flex flex-col gap-3">
          <h5>Comunidad</h5>
          <p>Noticias</p>
          <p>Discusiones</p>
          <p>Streaming</p>
          <p>Mentores</p>
          <p>Amigos</p>
        </div>
        <div class="flex flex-col gap-3">
          <h5>Soporte</h5>
          <p>Inicio de sesión</p>
          <p>Juegos</p>
          <p>Compras</p>
          <p>Mis puntos</p>
        </div>
      </div>
    </div>
    <div class="flex gap-3">
      <Button :icon="'community'" :littleIcon="true"></Button>
      <Button :icon="'community'" :littleIcon="true"></Button>
      <Button :icon="'community'" :littleIcon="true"></Button>
      <Button :icon="'community'" :littleIcon="true"></Button>
      <Button :icon="'community'" :littleIcon="true"></Button>
    </div>
    <div class="flex flex-col gap-16">
      <div class="flex justify-between">
        <p class="bold">Bread | Bread | Bread | Bread | Bread</p>
        <Button :icon="'community'" :littleIcon="true"></Button>
      </div>
      <div class="flex justify-between">
        <p>@2024 Steam. All rights reserved</p>
        <div class="flex">
          <p>Política y privacidad</p>
          <p>Términos y condiciones</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import Tag from "./mockComponents/Tag.vue";
import Button from "./mockComponents/Button.vue";
</script>

<style lang="sass" scoped></style>
