<template>
  <div :class="`${colors} ${padding} py-2 rounded-full h-fit flex justify-center`">
    <h4 v-if="ache4 == true" class="flex text-center">
      <slot></slot>
    </h4>
    <h3 v-else>
      <slot></slot>
    </h3>

    <template v-if="props.icon === 'search'">
      <ph-magnifying-glass :size="size" />
    </template>
    <template v-else-if="props.icon === 'community'">
      <ph-globe :size="size" />
    </template>
    <template v-else-if="props.icon === 'like'">
      <ph-heart-straight :size="size" />
    </template>
    <template v-else-if="props.icon === 'drop'">
      <ph-caret-down :size="size" />
    </template>
    <template v-else-if="props.icon === 'shop'">
      <ph-shopping-bag-open :size="size" />
    </template>
    <template v-else-if="props.icon === 'cart'">
      <ph-shopping-cart :size="32" />
    </template>


  </div>
</template>




<script setup>
import { defineProps } from "vue";
import {
  PhGlobe,
  PhShoppingBagOpen,
  PhMagnifyingGlass,
  PhCaretDown,
  PhHeartStraight,
  PhShoppingCart
} from "@phosphor-icons/vue";

const props = defineProps({
  color: String,
  icon: String,
  littleIcon: Boolean,
  littleText: Boolean,
});

let colors = "";

let size = "";
let padding = "px-5";
let ache4 = false;

// if (props.color === 'black') {
//     colors = 'bg-black text-white';
// } else if (props.color === 'gray') {
//     colors = 'bg-g300 text-g700';
// } else if (props.color === 'darkgray') {
//     colors = 'bg-g500 text-g700';
// } else if (props.color === 'primary') {
//     colors = 'bg-primary text-black';
// } else if (props.color === 'transparent') {
//     colors = 'bg-none text-black';
// }

if (props.color === "gray") {
  colors = "bg-g300 text-g700 grayh";
} else if (props.color === "primary") {
// bg-primary es tailwind
  colors = "bg-primary text-black primaryh";
} else if (props.color === "transparent") {
  colors = "bg-none text-black transparenth";
}

size = props.littleIcon ? "26" : "36";
if (props.icon !== undefined && props.icon !== "") {
  colors = "bg-g400 text-black grayh";
  padding = "px-2";
}
if (props.littleText !== undefined && props.littleText !== false) {
  ache4 = true;
}
</script>

<style lang="sass" scoped>
.grayh:hover
    @apply bg-g500 text-g700
.primaryh:hover
    box-shadow: inset 0px 0px 0px 2px black
    box-sizing: border-box
.transparenth:hover
    @apply bg-black text-white

.grayh:active
    @apply bg-g500 text-g100
.primaryh:active
    @apply bg-g100
    box-shadow: inset 0px 0px 0px 2px black
    box-sizing: border-box
.transparenth:active
    @apply bg-transparent text-black
    box-shadow: inset 0px 0px 0px 2px black
    box-sizing: border-box
</style>
