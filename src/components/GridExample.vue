<script setup>
import { ref } from 'vue';
import Resizeable from './Resizeable.vue';
const layout = [
  { x: 0, y: 0, w: 2, h: 2, i: 0 },
  { x: 2, y: 0, w: 2, h: 4, i: 1 },
  { x: 4, y: 0, w: 2, h: 5, i: 2 },
  { x: 6, y: 0, w: 2, h: 3, i: 3 },
  { x: 8, y: 0, w: 2, h: 3, i: 4 },
  { x: 8, y: 0, w: 2, h: 3, i: 5 },
  { x: 0, y: 5, w: 2, h: 5, i: 6 },
  { x: 2, y: 5, w: 2, h: 5, i: 7 },
  { x: 4, y: 5, w: 2, h: 5, i: 8 },
  { x: 6, y: 3, w: 2, h: 4, i: 9 },
];
</script>

<template>
  <GridLayout
    v-model:layout="layout"
    :col-num="12"
    :row-height="30"
    @resize="resize"
    @move="move"
    @moved="moved"
  >
    <template #default="{ gridItemProps }">
      <GridItem
        v-for="item in layout"
        :key="item.i"
        v-bind="gridItemProps"
        ref="gridItemRef"
        :x="item.x"
        :y="item.y"
        :w="item.w"
        :h="item.h"
        :i="item.i"
        :is-resizable="true"
        class="item"
      >
        <Resizeable />
      </GridItem>
    </template>
  </GridLayout>
</template>
