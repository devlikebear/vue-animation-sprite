<script setup lang="ts">
import { AnimationSprite } from "../../lib/main";
import { computed } from "vue";
import catImage from "../assets/cat.png";

const imageUrl = computed(() => {
  return catImage;
});
</script>
<template>
  <div>
    <animation-sprite
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
