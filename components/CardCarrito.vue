<template>
  <div :class="`card flex gap-5 p-6  rounded-3xl bg-g800 text-white`">
    <SquareImg class="w-[40%]" :url="props.img"></SquareImg>
    <div class="text flex flex-col gap-16">
      <h4>{{ props.name }}</h4>
      <p><slot></slot></p>

      <Button :color="'primary'" class="w-[150px]">13,95€</Button>
    </div>
  </div>
</template>

<script setup>
import Tag from "./mockComponents/Tag.vue";
import Button from "./mockComponents/Button.vue";



const props = defineProps({
  name: String,
  img: String,
});




</script>

<style lang="sass" scoped></style>
