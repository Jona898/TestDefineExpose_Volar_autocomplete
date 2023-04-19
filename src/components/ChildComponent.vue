<script setup lang="ts">
import { ref } from "vue";

const sum = ref(0);

const testFunctionAdd = (val1: number, val2: number) => {
  sum.value = val1 + val2;
};

defineExpose({ testFunctionAdd, sum });
</script>

<template>
  <div>
    <h2>Child Component:</h2>
    <p>Sum: {{ sum }}</p>
  </div>
</template>

<style scoped></style>
