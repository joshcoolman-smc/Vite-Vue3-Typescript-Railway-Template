<script setup lang="ts">
import { storeToRefs } from 'pinia';
import { useStateStore } from '../store/state';

defineProps<{ msg?: string }>()

const store = useStateStore()
const { name, doubleCount } = storeToRefs(store);
const { increment } = store;
</script>

<template>
  <div class="bg-slate-200 p-5">
    <h1 class="text-4xl font-bold text-slate-700 mb-5">Hello {{ name }} {{ doubleCount }}</h1>
    <button @click="increment" class="btn-primary">Count</button>
  </div>
</template>

<style scoped>

</style>
