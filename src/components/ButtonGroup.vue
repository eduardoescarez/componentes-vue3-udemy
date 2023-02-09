<script setup>
defineProps(["inicio", "fin", "cantidadElementos"])
const emit = defineEmits(["siguiente", "atras"])

</script>

<template>
    <div class="container text-center">
        <div class="btn-group" role="group" aria-label="Basic example">
            <button @click="emit('atras')" type="button" class="btn btn-primary" :disabled="inicio <= 0">Anterior {{ inicio }}</button>
            <button @click="emit('siguiente')" type="button" class="btn btn-primary" :disabled="fin >= cantidadElementos">Siguiente {{ fin }}</button>
        </div>
    </div>
</template>

