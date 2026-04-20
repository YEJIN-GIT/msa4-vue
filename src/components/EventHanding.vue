<script setup>
import { ref } from 'vue';

const cnt = ref(0);

function resetCnt(num) {
  cnt.value = num;
}
</script>

<template>
  <h1>이벤트 핸들링: {{ cnt }}</h1>
  <button type="button" @mousemove="cnt++">인라인 핸들러</button>
  <!-- vue에서는 즉시 함수를 호출하지않고 click되었을 때 resetCnt를 호출한다 -->
  <button type="button" @click="resetCnt(9)">메소드 핸들러</button>  <!-- @click="(() => resetCnt(9))" -->
  <input type="text" @keydown.up="cnt++" v-model="cnt">
</template>

<style>
</style>