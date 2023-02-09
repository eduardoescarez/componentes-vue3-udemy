<script setup>
const emit = defineEmits(['siguiente', 'atras'])

const activarSiguiente = () => {
    console.log("siguiente")
    emit('siguiente')
}
</script>

<template>
    <div class="container text-center">
        <div class="btn-group" role="group" aria-label="Basic example">
            <button @click="emit('atras')" type="button" class="btn btn-primary">Anterior</button>
            <button @click="activarSiguiente" type="button" class="btn btn-primary">Siguiente</button>
        </div>
    </div>
</template>

