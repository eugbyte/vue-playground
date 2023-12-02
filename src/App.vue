<script setup lang="ts">
import { computed, onMounted, ref, watch } from 'vue';
import Button from './components/Button.vue';

const text = ref("Increment");
const count = ref(0);
const handleClick = () => {
  count.value += 1;
}
onMounted(() => {
  console.log("component mounted");
});

watch(count, (newCount, oldCount) => {
  console.log(`old count is ${oldCount}`);
  console.log(`new count is ${newCount}`);
});

const squared = computed(() => Math.pow(count.value, 2));

const tailwindClass = "flex flex-row justify-center items-center h-screen border border-black text-white";
</script>

<template>
  <main class="container">
    <div >
      <p>{{ count }}</p>
      <p>Squared: {{ squared }}</p>
      <Button :onClick="handleClick" :text="text" />
      <label for="input">Button text:</label>
      <input id="input" v-model="text" >
    </div>
  </main>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  border: 1px black solid;
  height: 98vh;
  background-color: #C5B3A1;
}
</style>
