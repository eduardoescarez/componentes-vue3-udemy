<script setup>
defineProps(['title','id','body', 'colortext'])
</script>

<template>
    <div class="card">
        <div class="card-body">
            <h5 class="card-title" :class="`text-${colortext}`">
                {{ id }} - {{ title }}
            </h5>
            <p>{{ body }}</p>
        </div>
    </div>
</template>
