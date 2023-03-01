<script setup>
import {ref} from 'vue'
const number = ref(0)
const Counter =() => {number.value++}

</script>
<template>
    <div class="card card-body">
    <h1 class="card-title">Click para aumentar el contador</h1>
    <p class="card-text">Lorem ipsum dolor sit amet consectetur adipisicing elit. Officiis placeat inventore architecto, enim dicta rerum fuga. A qui ullam ipsam repellendus quibusdam error soluta delectus, saepe illum deserunt, incidunt accusantium.</p>
    <button @click="Counter" class="btn btn-primary">{{ number }}</button>
        </div>
</template>