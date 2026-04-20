<script setup>
// 자식 컴포넌트에서는 defineProps()르 이용해서 넘어온 데이터 선언
//  - 이때 부모 컴포넌트에서 넘겨줄 때 사용한 키를 사용해 선언
//  - 데이터 타입도 지정
defineProps(['cnt', 'page']);

// 아래와 같이 사용시, <template>에서 {{ props.cnt }}로 사용하여 cnt가 프롭스인지 개발자가 보기 쉽다.
// const props = defineProps({
//   'cnt': Number,
//   'page': Number,
// });

// 자식 컴포넌트에서는 defineEmits()를 이용해 넘어온 컴포넌트 이벤트 선언
//  - 이때 부모 컴포넌트에서 넘겨줄 때 사용한 이벤트 명을 사용해 선언
  defineEmits(['EventMinusCnt']);

//const emit = defineEmits(['EventMinusCnt']); 로 사용시 emit('EventMinusCnt', 10)
</script>

<template>
  <h1>{{ page }}프롭스 자식 컴포넌트: {{ cnt }}</h1>
  <button type="button" @click="$emit('EventMinusCnt', 10)">감소(자식쪽)</button>
</template>
<style scoped>

</style>