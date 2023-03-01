<script setup>
import {ref} from 'vue'
const number = ref(0)
const Counter =() => {number.value++}

</script>
<template>
    <div class="card card-body">
    <h1 class="card-title">Click para aumentar el contador</h1>
    <p class="card-text">illum deserunt, incidunt accusantium.</p>
    <div class="btn-group">
    <button @click="Counter" class="btn btn-primary">ShowPosts!{{ number }}</button>
    <button @click="Counter" class="btn btn-primary">ShowPosts!{{ number }}</button>
    </div>
        </div>
</template>
<style>
</style>