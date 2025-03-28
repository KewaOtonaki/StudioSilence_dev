<script setup>
import Contents from './components/Contents.vue'
import FetchMenu from './components/FetchMenu.vue'
</script>

<template>
  <div class="app-wrap">
    <FetchMenu />
    <Contents />
  </div>
</template>

<style scoped>
  .app-wrap {
    display: flex;
  }
</style>
