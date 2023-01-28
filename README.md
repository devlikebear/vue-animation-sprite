# DevForest Vue Animation Sprite

A simple animation sprite component.

Main features:

* Can use spritesheets
* Can specify specific animation areas from spritesheet
* Can adjust animation speed
* Can specify animation repeat count"

## Install

npm:
```shell
npm install devforest-vue-animation-sprite
```

## Use in Vue 3

```vue
<script setup lang="ts">
import DevforestVueAnimationSprite from "devforest-vue-animation-sprite";
import "devforest-vue-animation-sprite/dist/style.css";

import { computed } from "vue";
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
```

## Resources

* cat.png : https://elthen.itch.io/2d-pixel-art-cat-sprites