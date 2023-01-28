<script setup lang="ts">
/**
 * @displayName Anitmation Sprite
 */

import { computed } from "vue";

const props = withDefaults(
  defineProps<{
    /**
     * 스프라이트 너비
     */
    width?: number;
    /**
     * 스프라이트 높이
     */
    height?: number;
    /**
     * 스프라이트시트에서 애니메이션을 시작하는 첫 번째 스프라이트의 왼쪽 좌표
     */
    left?: number;
    /**
     * 스프라이트시트에서 애니메이션을 시작하는 첫 번째 스프라이트의 위 좌표
     */
    top?: number;
    /**
     * 스프라이트시트 이미지 경로
     */
    image?: string;
    /**
     * 한 세트의 애니메이션이 재생되는 시간
     */
    duration?: number;
    /**
     * 한 세트의 애니메이션을 구성하는 스프라이트의 개수
     */
    numOfAnimationSprite?: number;
    /**
     * 재생 횟수
     */
    iterationCount?: number | "infinite";
  }>(),
  {
    width: 32,
    height: 32,
    image: "",
    duaration: 1,
    numOfAnimationSprite: 4,
    iterationCount: 0,
    left: 0,
    top: 0,
  }
);

/**
 * 스프라이트시트에서 애니메이션이 끝나는 스프라이트의 위치
 */
const animateToLeftPosition = computed(() => {
  return props.width * props.numOfAnimationSprite * -1;
});

/**
 * 이미지경로는 url(...)함수에 쌓여 반환되어야 한다
 */
const imageUrl = computed(() => {
  return 'url("' + props.image + '")';
});
</script>
<template>
  <!-- 다음과 같이 inline style로 지정해도 된다 -->
  <!-- <div class="sprite" v-bind:style="{ backgroundImage: 'url(' + image + ')' }"></div> -->
  <div class="sprite"></div>
</template>
<style scoped lang="scss">
.sprite {
  width: calc(v-bind(width) * 1px);
  height: calc(v-bind(width) * 1px);
  background-image: v-bind(imageUrl);
  background-position: calc(v-bind(left) * 1px) calc(v-bind(top) * 1px);
  animation: play calc(v-bind(duration) * 1s) steps(v-bind(numOfAnimationSprite))
    v-bind(iterationCount);
}

@keyframes play {
  100% {
    background-position: calc(v-bind(animateToLeftPosition) * 1px) calc(v-bind(top) * 1px);
  }
}
</style>
