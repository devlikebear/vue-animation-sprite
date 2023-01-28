<script setup lang="ts">
import DevforestVueAnimationSprite from "../../lib/DevforestVueAnimationSprite.vue";
import { computed } from "vue";
// https://elthen.itch.io/2d-pixel-art-cat-sprites
import catImage from "../assets/cat.png";

const imageUrl = computed(() => {
  return catImage;
});
</script>
<template>
  <div>
    <DevforestVueAnimationSprite
      :width="32"
      :height="32"
      :image="imageUrl"
      :duration="1"
      :numOfAnimationSprite="8"
      :left="0"
      :top="32 * -9"
      iteration-count="infinite"
    />
  </div>
</template>
