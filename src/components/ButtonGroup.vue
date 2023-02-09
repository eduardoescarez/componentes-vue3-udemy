<script setup>
defineProps(["inicio", "fin"])
const emit = defineEmits(["siguiente", "atras"])

const activarSiguiente = () => {
    console.log("siguiente")
    emit('siguiente')
}
</script>

<template>
    <div class="container text-center">
        <div class="btn-group" role="group" aria-label="Basic example">
            <button @click="emit('atras')" type="button" class="btn btn-primary" :disabled="inicio <= 0">Anterior {{ inicio }}</button>
            <button @click="activarSiguiente" type="button" class="btn btn-primary" :disabled="fin >= 100">Siguiente {{ fin }}</button>
        </div>
    </div>
</template>

