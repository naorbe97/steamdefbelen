<template class="flex flex-col">
    <title>TiendaNuevos</title>
    <!-- <NavBar :shop="true" :primary="'nuevos'" class="sticky"></NavBar> -->
    <div class="flex w-[98vw] gap-[2%]">
        <section class="flex relative bgimage w-[48vw]">
            <NuxtLink to="/tiendaJuego"><CardJuegoDestacado :name="'El juegón'" class="absolute top-10 left-10">
                Juego elegido que mola que flipas, no te arrepentirás toda tu vida, está de oferta.
            </CardJuegoDestacado></NuxtLink>
        </section>
        <div class="flex flex-col py-11 px-22 gap-8">
            <div class="flex justify-between">
                <h3>Populares</h3>
                <Nuxtlink to="/tiendaNuevos"><h3 class="text-g500">Próximamente</h3></Nuxtlink>
            </div>
            <div class="scroll-container ">
                <div class="flex gap-10 overflow-x-scroll w-[46vw] scrollbar">

                    <CardJuego v-for="i in arrayJuegos" :img="i.img" :name="i.name" >
                        
                    </CardJuego>

                </div>
            </div>
            <div class="scroll-container ">
                <div class="flex gap-10 overflow-x-scroll w-[46vw] scrollbar">

                    <CardJuego v-for="i in arrayJuegos" :img="i.img" :name="i.name" >
                        
                    </CardJuego>

                </div>
            </div>
        </div>
    </div>
    <!-- <Footer></Footer> -->

</template>


<script setup>
import { inject } from 'vue'

// Inyectar la variable global
const arrayJuegos = inject('arrayJuegos')
</script>


<style lang="sass" scoped>

 .bgimage
    background-image: url('sampleimg.jpg')
    background-size: cover
    background-position: center

.scrollbar
    scrollbar-width: thin
    scrollbar-color: black white

</style>