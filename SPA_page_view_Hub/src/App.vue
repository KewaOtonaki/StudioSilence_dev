<script setup>
import Title from "./components/Title.vue"
import MathContents from "./components/math/MathContents.vue"
</script>

<template>
  <div class="screen">
    <Title></Title>
    <MathContents></MathContents>
  </div>
</template>

<style scoped>
  .screen{
    background-image: url("/src/assets/img/background49.png");
    background-size: cover;
    width: 100vw;
    height: 100vh;
    /*overflow: hidden;*/
  }

</style>
