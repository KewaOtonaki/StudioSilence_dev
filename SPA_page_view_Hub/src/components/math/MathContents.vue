<script setup>
import MathTitle from "./MathTitle.vue"
import Number from "./Number.vue"
import Arithmetic from "./Arithmetic.vue"
import Function from "./Function.vue"
import Figure from "./Figure.vue"
import Manifold from "./Manifold.vue"
import Logic from "./Logic.vue"
import Set from "./Set.vue"
</script>

<template>
    <div class="scrollable">
        <MathTitle></MathTitle>
        <Number></Number>
        <Arithmetic></Arithmetic>
        <Function></Function>
        <Figure></Figure>
        <Manifold></Manifold>
        <Logic></Logic>
        <Set></Set>
    </div>
</template>

<style>
.scrollable{
    height: 80vh;
    width: 100%;
    overflow: auto;
}
</style>