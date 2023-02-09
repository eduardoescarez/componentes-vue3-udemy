<script setup>
import { ref, computed } from "vue";
import BlogPost from "./components/BlogPost.vue"
import ButtonGroup from "./components/ButtonGroup.vue"
import LoadingSpinner from "./components/LoadingSpinner.vue"

const posts = ref([])
const postxpagina = ref(10)
const inicio = ref(0)
const fin = ref(postxpagina.value)
const loading = ref(true)

const favorito = ref("")

const cambiarFavorito = (title) => {
    favorito.value = title
}

const siguiente = () => {
    inicio.value += postxpagina.value
    fin.value += postxpagina.value
}

const atras = () => {
    inicio.value -= postxpagina.value
    fin.value -= postxpagina.value
}


fetch("https://jsonplaceholder.typicode.com/posts")
    .then(res => res.json())
    .then(data => {posts.value = data})
    .catch((e) => console.log(e))
    .finally(() => (loading.value = false))

const cantidadEntradas = computed(() => posts.value.length)

</script>


<template>
    <LoadingSpinner v-if="loading"/>
    <div class="container" v-else>
        <h1>APP</h1>
        <h2>Mi post favorito: {{ favorito }}</h2>


        <ButtonGroup @siguiente="siguiente" @atras="atras" :inicio="inicio" :fin="fin" :cantidadElementos="cantidadEntradas" class="mb-2"/>

        <BlogPost
            v-for="post in posts.slice(inicio, fin)"
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