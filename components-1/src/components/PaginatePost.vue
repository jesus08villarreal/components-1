<script setup>
defineProps({anteriorHabilitado: Boolean,
siguienteHabilitado: Boolean})
</script>
<template>
<div class="btn-group" role="group" aria-label="Basic example">
  
  <button
  :disabled=anteriorHabilitado
   @click="$emit('PaginaAnterior')"
    type="button" 
    class="btn btn-outline-primary"
    >Previus</button>


  <button 
  :disabled=siguienteHabilitado
  @click="$emit('PaginaSiguiente')"
   type="button"
    class="btn btn-outline-primary"
    >Next</button>

</div>

</template>
<style>
</style>