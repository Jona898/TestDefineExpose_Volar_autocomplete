<script setup lang="ts">
import { ref } from "vue";
import ChildComponent from "./ChildComponent.vue";

const numb1 = ref(0);
const numb2 = ref(0);

const childRef = ref<typeof ChildComponent | null>(null);
</script>

<template>
  <div>
    <h2>ParentComponent</h2>
    <div>
      <label for="numb1">Number1</label>
      <input type="number" name="numb1" id="numb1" v-model="numb1" />
    </div>
    <div>
      <label for="numb2">Number2</label>
      <input type="number" name="numb2" id="numb2" v-model="numb2" />
    </div>
    <div>
      <button @click="() => childRef!.testFunctionAdd(numb1, numb2)">
        Activate child Function
      </button>
    </div>
    <p>Child Sum: {{ childRef!.sum }}</p>
  </div>

  <br />

  <ChildComponent ref="childRef"></ChildComponent>
</template>

<style scoped></style>
