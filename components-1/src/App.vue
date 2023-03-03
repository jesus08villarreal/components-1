<script setup>
import ButtonCounter from './components/ButtonCounter.vue'
import BlogPost from './components/BlogPost.vue'
import {ref} from 'vue'

const posts = ref([
  {title: "Alex", id: 1,body:"descripcion 1", btntext:"Favorito"},
  {title: "Yisus", id: 2,body:"descripcion: 2", btntext:"Favorito"},
  {title: "Maylon", id: 3,body:"descripcion 3", btntext:"Favorito"},
  {title: "Ricarda", id: 4,body:"descripcion 4", btntext:"Favorito"},
  {title: "Charby", id: 5,body:"descripcion 5", btntext:"Favorito"},
  {title: "Puchis", id: 4, btntext:"Puchis"},
])
const favoritoEscogido = ref('')
const cambiarFavorito =(title)=>{ favoritoEscogido.value = title}
</script>

<template>
  <h1>APP</h1>
  <h2>Mi post favorito: {{ favoritoEscogido }}</h2>
  <BlogPost
  v-for="post in posts"
  :key="post.id"
   :title="post.title"
    :btntext="post.btntext"
      :body="post.body"
        :id="post.id"
        @cambiarFavorito="cambiarFavorito"
    >
    </BlogPost>



</template>

<style>

</style>
