<script setup>
    import ButtonCounter from "./components/ButtonCounter.vue"
    import BlogPost from "./components/BlogPost.vue"
</script>


<template>
    <div class="container">
        <h1>APP</h1>
        <ButtonCounter/>
        <BlogPost title="Post 1" id="1" body="descripcion 1" colortext="primary"/>
        <BlogPost title="Post 2" id="2" body="descripcion 1" colortext="secondary"/>
        <BlogPost title="Post 3" id="3" body="descripcion 1" colortext="success"/>
        <BlogPost title="Post 4" id="4" body="descripcion 1" colortext="primary"/>
    </div>
</template>