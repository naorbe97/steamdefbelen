<template>
    <title>TiendaPuntos</title>
    <div class="flex flex-col relative">
    <div class="flex p-11 gap-8">
        <p class="text-primary">MIS PUNTOS</p>
        <p>200</p>
    </div>
  <div class="flex flex-col gap-24">
    <div class="flex px-11 overflow-x-scroll  scrollbar gap-2.5">
        <CardJuegoMes v-for="i in arrayJuegos" :color="'dark'" :name="i.name" :img="i.img" >
                    I have a dashboard with two sides, a nav on the left and the main content on the right, simple. They
                    both are housed by a main div which has the height of the current screen. I need the main content
                    div to scroll internally not scroll with the entire view when content overflows. All this while the
                    nav on the right remains as is without being affected by the content overflow on the main content
                    div
        </CardJuegoMes>
    
        
    </div>
    <div class="flex px-11 overflow-x-scroll  scrollbar gap-2.5">
        <CardJuegoMes v-for="i in arrayJuegos" :color="'dark'" :name="i.name" :img="i.img" >
                    I have a dashboard with two sides, a nav on the left and the main content on the right, simple. They
                    both are housed by a main div which has the height of the current screen. I need the main content
                    div to scroll internally not scroll with the entire view when content overflows. All this while the
                    nav on the right remains as is without being affected by the content overflow on the main content
                    div
        </CardJuegoMes>
      
        
    </div> 
    <div class="flex px-11 overflow-x-scroll  scrollbar gap-2.5">
        <CardJuegoMes v-for="i in arrayJuegos" :color="'dark'" :name="i.name" :img="i.img" >
                    I have a dashboard with two sides, a nav on the left and the main content on the right, simple. They
                    both are housed by a main div which has the height of the current screen. I need the main content
                    div to scroll internally not scroll with the entire view when content overflows. All this while the
                    nav on the right remains as is without being affected by the content overflow on the main content
                    div
        </CardJuegoMes>
        
    </div>
  </div>
    

</div>
</template>


<script setup>
let dropdown = ref(true)
const dropdownModal = () => {
    dropdown.value = !dropdown.value
}
import { inject } from 'vue'

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