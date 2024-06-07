<template>
    <title>Inicio</title>
    <LoginModal :opened="loginModal"></LoginModal>
    <div class="flex flex-col items-center gap-20 bg-gradient-to-b from-primary to-g700 from-10% to-90% py-40">
      <img src="/favicon.ico" alt="" class="w-[20%] object-contain">
      <h1 class=" rounded-full k " @click="seeModal">Inicia sesión</h1>
      <div class="flex flex-col items-center gap-12">
        <h4>
          Steam es el mejor lugar para jugar, hablar sobre juegos y crearlos
        </h4>
        <div class="flex items-center gap-20">
          <div class="flex flex-col items-center gap-4">
            <h3>
              Jugando
            </h3>
            <h2>
              4,546,790
            </h2>
          </div>
          <div class="flex flex-col items-center gap-4">
            <h3>
              En línea
            </h3>
            <h2>
              13,255,986
            </h2>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  import SquareImg from '~/components/SquareImg.vue';
  import Button from '~/components/mockComponents/Button.vue';
  import LoginModal from '~/components/LoginModal.vue';
  
  let loginModal = ref(false);
  let filtro = false
  
  const seeModal = () => {
    loginModal.value = !loginModal.value;
  };
  </script>

<style lang="sass" scoped>

.k
    @apply bg-transparent text-black p-6
    box-shadow: inset 0px 0px 0px 8px black
    box-sizing: border-box
.k:hover
    @apply bg-primary text-black p-6
    box-shadow: inset 0px 0px 0px 4px black
    box-sizing: border-box

</style>
