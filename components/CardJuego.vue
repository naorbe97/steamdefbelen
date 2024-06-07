<template>
  <div class="card w-fit flex flex-col gap-3">
    <div class="flex flex-col p-7 rounded-3xl gap-5 bg-g800">
      <SquareImg class="w-72" :url="props.img"></SquareImg>
      <div class="downButtons flex gap-5 items-center">
        <Button :color="'primary'" @click="sumarItems()">{{ price }}€</Button>
        <Button :icon="'shop'" @click="sumarItems()"> </Button>
        <Button :icon="'like'"></Button>
      </div>
    </div>
    <div class="text flex justify-between">
      <h4>{{ props.name }}</h4>
      <Tag></Tag>
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
  img: String,
  price: String,
  name: String
});

let price = "";
price = props.price;
if (price == "" || price == undefined) {
  price = "13.95";
}
const sumarItems = () =>{
  itemsInCart.value.push(props.name)
  console.log(itemsInCart.value)
  console.log('hola')

}
</script>

<style lang="sass" scoped></style>
