<script setup>
import { ref } from "vue";
import BlogPost from "./components/BlogPost.vue"
import ButtonGroup from "./components/ButtonGroup.vue"

const posts = ref([])

const favorito = ref("")

const cambiarFavorito = (title) => {
    favorito.value = title
}

fetch("https://jsonplaceholder.typicode.com/posts")
    .then(res => res.json())
    .then(data => {posts.value = data})

</script>


<template>
    <div class="container">
        <h1>APP</h1>
        <h2>Mi post favorito: {{ favorito }}</h2>
        <ButtonGroup class="mb-2"/>
        <BlogPost
            v-for="post in posts.slice(0, 10)"
            :key="post.id"
            :title="post.title"
            :id="post.id"
            :body="post.body"
            @cambiarFavoritoNombre="cambiarFavorito"
            class="mb-2"
            >
        </BlogPost>
    </div>
</template>