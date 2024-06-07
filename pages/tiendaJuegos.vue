<template class="flex flex-col">
    <title>TiendaJuegos</title>
    <!-- <NavBar :shop="true" :primary="'juegos'" class="sticky"></NavBar> -->
    <div class="flex flex-col p-11 gap-11">
        <Dropdown @click="Dropdown()"></Dropdown>
        <div class="flex gap-10 overflow-x-scroll  scrollbar">
            <CardJuegoMes v-for="i in arrayJuegos" :color="'dark'" :name="i.name" :img="i.img" >
                    I have a dashboard with two sides, a nav on the left and the main content on the right, simple. They
                    both are housed by a main div which has the height of the current screen. I need the main content
                    div to scroll internally not scroll with the entire view when content overflows. All this while the
                    nav on the right remains as is without being affected by the content overflow on the main content
                    div
            </CardJuegoMes>
            
        </div>
    </div>
    <!-- <Footer></Footer> -->

</template>


<script setup>
import { inject } from 'vue'
import Dropdown from '~/components/Dropdown.vue';

// Inyectar la variable global
const arrayJuegos = inject('arrayJuegos')
</script>


<style lang="sass" scoped>

//  .bgimage
//     background-image: url('sampleimg.jpg')
//     background-size: cover
//     background-position: center

.scrollbar
    scrollbar-width: thin
    scrollbar-color: black white

</style>