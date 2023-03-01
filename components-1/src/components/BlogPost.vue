<script setup>
defineProps(['title'])
</script>
<template>
    <div class="card">
    <div class="card-body">
        <h1 class="card-title">{{ title }}</h1>
            <h5 class="card-text">Lorem ipsum dolor sit amet.</h5>
                <button class="btn btn-info">Mas!</button>
    </div>
    </div>
</template>
<style>

</style>