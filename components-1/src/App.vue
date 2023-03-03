<script setup>
import PaginatePost from './components/PaginatePost.vue'
import BlogPost from './components/BlogPost.vue'
import {ref} from 'vue'



const posts = ref([

])
const favoritoEscogido = ref('')
const cambiarFavorito =(title)=>{ favoritoEscogido.value = title}

fetch("https://jsonplaceholder.typicode.com/posts")
.then(response => response.json())
      .then(data => posts.value = data)
</script>

<template>
  <nav class="navbar navbar-expand-lg bg-body-tertiary">
  <a class="text-center backgroundTitle navbar-brand" href="">The Post!</a>
  <PaginatePost></PaginatePost>
  </nav>

  <h2 class="padre1">Mi post favorito: {{ favoritoEscogido }}</h2>

  <div  class="padre1">
  <BlogPost
  v-for="post in posts"
  :key="post.id"
   :title="post.title"
    btntext="Iniciar"
      :body="post.body"
        :id="post.id"
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
.navbar {

}
.backgroundTitle {
  background-color: grey;
  color: white;
  padding: 1rem;
}
</style>
