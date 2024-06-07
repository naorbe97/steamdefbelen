<template>
    <title>Streaming</title>
    <div class="flex flex-col gap-8 p-20 bg-g300 ">

        <div class="flex flex-col items-center">
            <CardCarrito :img="arrayJuegos[0].img" :name="`${arrayJuegos[0].name}`" class="w-[70%]"> I have a
            dashboard with two sides, a nav on the left and the main content on the right, simple. They
            both are housed by a main div which has the height of the current screen. I need the main content
            div to scroll internall
            </CardCarrito>
        </div>
        <div class="flex flex-col gap-12 overflow-x-scroll scrollbar">
            <h1 class="text-black">
                Comentarios
            </h1>
            <div class="flex gap-12">
                <!-- gggggggggggggggggggg -->
                <CardComentario ></CardComentario>
                <CardComentario ></CardComentario>
                <CardComentario ></CardComentario>
                
                <CardComentario ></CardComentario>
                <CardComentario ></CardComentario>
                <CardComentario ></CardComentario>
                <CardComentario ></CardComentario>
                <CardComentario ></CardComentario>
                <CardComentario ></CardComentario>
                <CardComentario ></CardComentario>
                
                

                <!-- gggggggggggggggggggg -->
            </div>
        </div>
        <div class="flex flex-col gap-12">
            <h1 class="text-black">
                Juegos relacionados
            </h1>
            <div class="flex gap-12 overflow-x-scroll scrollbar">
                <!-- gggggggggggggggggggg -->
                <CardJuego v-for="i in arrayJuegos" :img="i.img" :name="i.name"></CardJuego>

                

                <!-- gggggggggggggggggggg -->
            </div>
        </div>
    </div>
</template>



<script setup>
import { ref } from 'vue';
import { inject } from 'vue'
import CardCarrito from '~/components/CardCarrito.vue';
import CardJuegoDestacado from '~/components/CardJuegoDestacado.vue';

// Inyectar la variable global
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