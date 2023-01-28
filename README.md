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
import { DevforestVueAnalogClock } from "devforest-vue-analog-clock";
import "devforest-vue-analog-clock/dist/style.css";

...
</script>
<template>

    <div>
        <DevforestVueAnalogClock 
        :size="200" 
        :second-hand-height="90" 
        :minute-hand-height="70" 
        :hour-hand-height="50" />
    </div>
</template>
```

## Resources

* cat.png : https://elthen.itch.io/2d-pixel-art-cat-sprites