<script setup lang="ts">
defineProps<{
  text: string,
  onClick: () => void;
}>()
</script>

<template>
  <div class="greetings">
    <button class="green" @click="onClick">{{text}}</button>
  </div>
</template>

<style scoped>
</style>
