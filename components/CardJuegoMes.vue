<template>
  <div :class="`card flex flex-col gap-5 ${textColor} p-6 w-[400px] rounded-3xl ${background} `">
    <div class="topTags flex gap-2">
      <Tag></Tag>
      <Tag></Tag>
    </div>
    <NuxtLink to="/tiendaJuego"><SquareImg class="w-fill" :url="props.img"></SquareImg></NuxtLink>
    <div class="text flex flex-col gap-16">
      <NuxtLink to="/tiendaJuego"><h4>{{ props.name }}</h4></NuxtLink>
      <NuxtLink to="/tiendaJuego"><p class="text-primary">New Release</p></NuxtLink>
      <p>
        <slot></slot>
      </p>
      <div class="downBottoms flex gap-5 items-center">
        <Button :color="'primary'" @click="sumarItems()">13,95€</Button>
        <Button :icon="'shop'" @click="sumarItems()"> </Button>
        <Button :icon="'like'"></Button>
      </div>
    </div>
  </div>
</template>

<script setup>
import Tag from "./mockComponents/Tag.vue";
import Button from "./mockComponents/Button.vue";

import { inject } from 'vue'

// Inyectar la variable global
const itemsInCart = inject('itemsInCart')

const props = defineProps({
  color: String,
  name: String,
  img: String,
});

const sumarItems = () => {
  itemsInCart.value.push(props.name)
  console.log(itemsInCart.value)
  console.log('hola')

}


let background = "";
let textColor = "";
if (props.color == "dark") {
  background = "bg-g800";
  textColor = "text-white";
} else if (props.color == "light") {
  background = "bg-g100 box-border border-2 border-black";
  textColor = "text-black";
}
</script>

<style lang="sass" scoped></style>
