<script setup>
defineProps(["anteriorHabilitado","siguienteHabilitado"])
</script>
<template>
<div class="btn-group" role="group" aria-label="Basic example">
  
  <button
  :disabled="anteriorHabilitado"
   @click="$emit('PaginaAnterior')"
    type="button" 
    class="btn btn-primary"
    >Previus</button>


  <button 
  :disabled="siguienteHabilitado"
  @click="$emit('PaginaSiguiente')"
   type="button"
    class="btn btn-primary"
    >Next</button>

</div>

</template>
<style>
</style>