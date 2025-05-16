<script setup>
import Title from "./components/Title.vue"
import Menu from "./components/Menu.vue"
import MathContents from "./components/math/MathContents.vue"
</script>

<template>
  <div class="bg">
    <Title></Title>
    <Menu></Menu>
  
    <div class="content">
      <MathContents></MathContents>
    </div>
  </div>
</template>

<style scoped>

</style>
