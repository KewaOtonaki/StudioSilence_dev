<script setup>
import Title from "./components/Title.vue"
import Menu from "./components/Menu.vue"
import MathContents from "./components/math/MathContents.vue"
import ComputerContents from "./components/computer/ComputerContents.vue"

import { ref } from 'vue';

const current = ref('mathematics');

function handleSelect(name) {
  current.value = name
}
</script>

<template>
  <div class="bg">
    <Title></Title>
    <Menu @select="handleSelect"></Menu>
  
    <div class="content">
      <div v-if="current === 'mathematics'"><MathContents></MathContents></div>
      <div v-if="current === 'computer'"> <ComputerContents></ComputerContents> </div>
    </div>
  </div>
</template>

<style>
</style>