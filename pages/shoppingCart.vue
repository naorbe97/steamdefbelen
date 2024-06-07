<template>
    <title>Carrito</title>
  
  <div class="flex flex-col gap-10 w-fill p-20">
      <CardCarrito v-for="i in arrayComprar" :name="i.name" :img="i.img" class="w-fill">
        Establece y expande tus propios asentamientos, libera la tierra y ayuda a sus aldeanos. Recluta a otros para tu causa mientras aprendes más sobre la vida que tuviste que dejar atrás. Dirige a tus fuerzas, demuestra tu valor en el combate y consolida tu lugar como el héroe de tu pueblo.
      </CardCarrito>
      <h3 v-if="arrayComprar.length === 0" class="text-center">Aún no has añadido Juegos a tu carrito :(</h3>
      <Button v-else :color="'primary'"> Comprar </Button>
      <div class="flex gap-10 overflow-x-scroll scrollbar">
        <CardJuego v-for="i in arrayJuegos" :name="i.name" :img="i.img">
        </CardJuego>
      </div>
  </div>
  
  </template>
  
  <script setup>
  import { ref } from 'vue';
  import SquareImg from '~/components/SquareImg.vue';
  import Button from '~/components/mockComponents/Button.vue';
  import LoginModal from '~/components/LoginModal.vue';
  import { inject } from 'vue'

  const itemsInCart = inject('itemsInCart')
  const arrayJuegos = inject('arrayJuegos')
  const arrayComprar = ref([])

  for (let itemName of itemsInCart.value) {
  
  const juego = arrayJuegos.value.find(juego => juego.name === itemName);
  
  if (juego) {
    arrayComprar.value.push(juego);
  }
}
  
  </script>
<style lang="sass" scoped>
</style>