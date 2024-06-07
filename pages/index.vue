<template>
    <title>TiendaJuegos</title>
    <div class="flex flex-col relative">
        <div class="flex flex-col  gap-8">
            <section class="flex relative bgimage w-full h-[70vh] rounded-3xl mb-11">
                <NuxtLink to="/tiendaJuego">
                    <CardJuegoDestacado :name="'El juegón'" class="absolute top-10 left-10">
                    Juego elegido que mola que flipas compratelo o te arrepentiras toda tu vida, está de oferta o algo
                    no se
                    que significa exactamente esta card
                </CardJuegoDestacado></NuxtLink>
            </section>
            <div class="flex justify-center">
                <CardCarrito :img="arrayJuegos[0].img" :name="arrayJuegos[0].name" class="w-[70%]"> I have a dashboard
                    with
                    two sides, a nav on the left and the main content on the right, simple. They
                    both are housed by a main div which has the height of the current screen. I need the main content
                    div to scroll internall</CardCarrito>
            </div>
            <div class="scroll-container ">
                <div class="flex gap-10 overflow-x-scroll scrollbar">
                    <CardJuegoMes v-for="i in arrayJuegos" :color="'dark'" :name="i.name" :img="i.img">
                        I have a dashboard with two sides, a nav on the left and the main content on the right, simple.
                        They
                        both are housed by a main div which has the height of the current screen. I need the main
                        content
                        div to scroll internally not scroll with the entire view when content overflows. All this while
                        the
                        nav on the right remains as is without being affected by the content overflow on the main
                        content
                        div
                    </CardJuegoMes>
                </div>
            </div>
        </div>
    </div>
</template>


<script setup>
import { ref } from 'vue';
import { inject } from 'vue'
const arrayJuegos = inject('arrayJuegos')
let dropdown = ref(false)
const dropdownModal = () => {
    dropdown.value = !dropdown.value
}
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