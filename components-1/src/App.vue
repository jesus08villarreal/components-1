<script setup>
import ButtonCounter from './components/ButtonCounter.vue'
import BlogPost from './components/BlogPost.vue'
import {ref} from 'vue'

const posts = ref([
  {title: "Post 1", id: 1,body:"descripcion 1", btntext:"Alex"},
  {title: "Post: 2", id: 2,body:"descripcion: 2", btntext:"Yisus"},
  {title: "Post 3", id: 3,body:"descripcion 3", btntext:"Maylon"},
  {title: "Post 4", id: 4, btntext:"Puchis"},
])

</script>

<template>
  <ButtonCounter/>
  <BlogPost
  v-for="post in posts"
  :key="post.id"
   :title="post.title"
    :btntext="post.btntext"
      :body="post.body"
        :id="post.id"
    >
    </BlogPost>



</template>

<style>

</style>
