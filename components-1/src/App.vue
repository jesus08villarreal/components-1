<script setup>
import PaginatePost from './components/PaginatePost.vue'
import BlogPost from './components/BlogPost.vue'
import Spinner from './components/LoadingSpinner.vue'
import {ref} from 'vue'

const Slice1 = ref(0)
const Slice2 = ref(5)
const pgXpg = 5
const posts = ref([])
const favoritoEscogido = ref('')
const anteriorHabilitado = ref(true)
const siguienteHabilitado = ref(false)

const cambiarFavorito =(title)=>{ favoritoEscogido.value = title}

const PaginaSiguiente = () => {
  anteriorHabilitado.value = false
  if(Slice2.value >= posts.value.length-pgXpg){
siguienteHabilitado.value = true
} 
  Slice1.value=Slice1.value+pgXpg
  Slice2.value=Slice2.value+pgXpg
}
const PaginaAnterior = () => {
  siguienteHabilitado.value = false
  Slice1.value=Slice1.value-pgXpg
  Slice2.value=Slice2.value-pgXpg
  if(Slice1.value <= 1){
anteriorHabilitado.value = true
}
}





fetch("https://jsonplaceholder.typicode.com/posts")
.then(response => response.json())
      .then(data => posts.value = data)
</script>

<template>
  <nav class="navbar navbar-expand-lg bg-body-tertiary">
  <a class="text-center backgroundTitle navbar-brand" href="">The Post!</a>
  <PaginatePost 
    @PaginaSiguiente="PaginaSiguiente()"
    @PaginaAnterior="PaginaAnterior()"
    :anteriorHabilitado=anteriorHabilitado
    :siguienteHabilitado=siguienteHabilitado
  ></PaginatePost>
  
    <Spinner/>
  
  </nav>

  <h2 class="padre1">Mi post favorito: {{ favoritoEscogido }}</h2>

  <div  class="padre1">
  <BlogPost
  v-for="post in posts.slice(Slice1,Slice2)"

  :key="post.id"
   :title="post.title"
    btntext="Iniciar"
      :body="post.body"
        :id="post.id"
        class="mb-2"
            :cambiarFavorito="cambiarFavorito"
    >
    </BlogPost>
  </div>



</template>

<style>

.padre1 {
    display: grid;
    grid-template-columns: 1fr;
    grid-auto-rows: 100px, auto;
    row-gap: 2rem;
    column-gap: 2rem;
    align-content: center;
    align-items: center;
    margin-bottom: 1rem;
    height: auto;
}

.backgroundTitle {
  background-color: grey;
  color: white;
  padding: 1rem;
}
</style>
