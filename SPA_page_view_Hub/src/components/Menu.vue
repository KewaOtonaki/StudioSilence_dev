<script setup>
const emit = defineEmits(['select'])

function select(name) {
  emit('select', name)
}
</script>


<template>
    <div>
        <div class="inline-block menu-item"><a href="#" @click="select('mathematics')">数学</a></div>
        <div class="inline-block menu-item"><a href="#" @click="select('computer')">コンピュータ</a></div>
        <div class="inline-block menu-item"><a href="#" @click="select('phylosophy')">哲学</a></div>
        <div class="inline-block menu-item"><a href="#" @click="select('music')">音楽</a></div>
    </div>
</template>

<style scoped>
  .inline-block {
    display: inline-block;
  }

  .menu-item {
    background-color: white;
    font-size: 2rem;
    text-align: center;
    height: 3rem;
    width:25%;
  }
</style>