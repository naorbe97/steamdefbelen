<template>
  <div
    class="rounded-3xl border-2 border-black aspect-square image"
    :style="{ backgroundImage: 'url(' + props.url + ')' }"
  ></div>
</template>

<script setup>
import Tag from "./mockComponents/Tag.vue";
import Button from "./mockComponents/Button.vue";

const props = defineProps({
  url: String,
});
</script>

<style lang="sass" scoped>
.image
    background-size: cover
    background-position: center
</style>
