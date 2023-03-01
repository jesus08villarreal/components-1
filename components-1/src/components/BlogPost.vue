<script setup>
import {ref} from 'vue'
defineProps({
title: String,
body: {
    type: String,
    default: "sin descripcion",
},
id: Number,
btntext: String
 })
</script>
<template>
    <div class="card">
    <div class="card-body">
        <h1 class="card-title">{{ title }}</h1>
            <h5 class="card-text">{{ body }}</h5>
                <p class="">{{ id }}</p>
                <button class="btn btn-info">{{btntext}}</button>
    </div>
    </div>
</template>
<style>

</style>