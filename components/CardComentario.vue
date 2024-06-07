<template>
    <div class="flex flex-col gap-6 rounded-2xl bg-g800 text-white p-8">
        <div class="flex justify-between">
            <img src="/user.png" class="rounded-full border-black border-2 w-20 h-20"></img>

            <div class="flex flex-col">
                <h4>
                    Username12
                </h4>
                <p>
                    Noland, 3 days ago
                </p>
            </div>
        </div>
        <p class="w-96">
            Establece y expande tus propios asentamientos, libera la tierra y ayuda a sus aldeanos.
            Recluta a otros para tu causa mientras aprendes más sobre la vida que tuviste que dejar atrás.
            Dirige a tus fuerzas, demuestra tu valor en el combate y consolida tu lugar como el héroe de tu pueblo.
        </p>
        <div class="flex justify-between">
            <h2 class="text-primary">
                4.5
            </h2>
            <Button :icon="'like'"></Button>
        </div>
    </div>
</template>

<script setup>
import Tag from "./mockComponents/Tag.vue";
import Button from "./mockComponents/Button.vue";
</script>

<style lang="sass" scoped></style>