<script setup>
import CosineLaw from './components/CosineLaw.vue';
import AsymptoteFinder from './components/AsymptoteFinder.vue';
import Approximation from "./components/Approximation.vue"
</script>

<template>
  <div class="Calculator">
    <CosineLaw />
    <AsymptoteFinder />
  </div>
  <Approximation />
</template>

<style scoped>
.Calculator {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
}
</style>