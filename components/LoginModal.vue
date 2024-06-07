<template>
    <div v-if="realOpened" class="flex flex-col fixed top-0 left-0 w-screen h-screen">
      <div class="bg-black w-screen h-screen absolute top-0 left-0 opacity-20" @click="toggleOpened"></div>
      <div v-if="registerModal" class="flex absolute z-20 top-[13%] left-[28%] bg-white rounded-3xl justify-center p-10 gap-20 w-[700px]">
        <div class="flex flex-col gap-8">
          <h2>Crea una cuenta en Steam</h2>
          <p class="mono text-g400 border-b-2 border-black">Nombre real</p>
          <p class="mono text-g400 border-b-2 border-black">Usuario</p>
          <p class="mono text-g400 border-b-2 border-black">Correo electrónico</p>
          <p class="mono text-g400 border-b-2 border-black">Repetir contraseña</p>
        </div>
        <div class="flex flex-col justify-center items-center gap-6">
          <img src="/public/QR.svg" alt="" class="w-32">
          <p class="mono text-center">Descárgate la app en tu smartphone usando este código QR</p>
          <Button :color="'primary'" @click="toggleOpened">Registrate</Button>
          <Button :color="'gray'" @click="seeRegister">Inicia sesión</Button>
        </div>
      </div>
      <div v-else class="flex flex-col absolute top-[13%] left-[38%] bg-white rounded-3xl justify-center p-10 gap-20 w-96">
        <h2 class="text-center">Inicia sesión en steam</h2>
        <div class="flex flex-col justify-center gap-10">
          <p class="mono text-g400 border-b-2 border-black">Usuario</p>
          <p class="mono text-g400 border-b-2 border-black">Contraseña</p>
          <Button :color="'primary'" @click="toggleOpened">Inicia sesión</Button>
          <Button :color="'gray'" @click="seeRegister">Regístrate</Button>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref, watch } from 'vue';
  import Button from './mockComponents/Button.vue';
  import { inject } from 'vue'

// Inyectar la variable global
  const navBarLogged = inject('navBarLogged') 
  
  const props = defineProps({
    opened: Boolean
  });
  
  let realOpened = ref(props.opened);
  let registerModal = ref(false);
  
  const toggleOpened = () => {
    realOpened.value = !realOpened.value;
    navBarLogged.value = !navBarLogged.value;
  };
  
  const seeRegister = () => {
    registerModal.value = !registerModal.value;
  };
  
  watch(() => props.opened, (newVal) => {
    realOpened.value = newVal;
  });
  </script>

<style lang="sass" scoped>

</style>
