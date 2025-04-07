<script setup>
import Contents from './components/Contents.vue'
import FetchMenu from './components/FetchMenu.vue'
</script>

<template>
  <div class="app-wrap margin-0px">
    <FetchMenu />
    <Contents class="margin-0px" />
  </div>
</template>

<style scoped>
  .app-wrap {
    display: flex;
  }
</style>
