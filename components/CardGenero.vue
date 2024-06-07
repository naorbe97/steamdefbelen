<template>
<NuxtLink to="tiendaJuegos">
  <div
    class="card flex py-8 relative w-fit rounded-3xl bg-white border-2 border-black"
  >
    <Button :color="'primary'" class="absolute top-[43%] left-10">
      <slot></slot>
    </Button>
    <div class="cont flex w-[500px] justify-center">
      <SquareImg class="h-72" :url="url"></SquareImg>
    </div>
  </div>
</NuxtLink>
</template>

<script setup>
import Tag from "./mockComponents/Tag.vue";
import Button from "./mockComponents/Button.vue";
const props = defineProps({
  img: String,
});
let url = "";
if (props.img == "" || props.img == undefined) {
  url = "sampleimg.jpg";
} else {
  url = props.img;
}
</script>

<style lang="sass" scoped></style>
