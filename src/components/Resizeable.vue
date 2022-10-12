<script setup>
import { ref } from 'vue';
const values = ref([]);
function add() {
  values.value.push('hello!');
}
</script>

<template>
  <div @click="add">Add</div>
  <div v-for="v in values">
    {{ v }}
  </div>
</template>
