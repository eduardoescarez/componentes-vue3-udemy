<script setup>
import { ref } from "vue";
import ButtonCounter from "./components/ButtonCounter.vue"
import BlogPost from "./components/BlogPost.vue"

const posts = ref([
    { id: 1, title: "Post 01", body: "Descrión del post 01" },
    { id: 2, title: "Post 02", body: "Descrión del post 02" },
    { id: 3, title: "Post 03", body: "Descrión del post 03" },
    { id: 4, title: "Post 04"},
])
</script>


<template>
    <div class="container">
        <h1>APP</h1>
        <ButtonCounter/>
        <BlogPost
            v-for="post in posts"
            :key="post.id"
            :title="post.title"
            :id="post.id"
            :body="post.body"
            >
        </BlogPost>
    </div>
</template>