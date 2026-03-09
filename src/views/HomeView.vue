<template>

    <h1 class="text-center">Página Home</h1>

    <button @click="disminuirContador" class="btn btn-primary mx-1">Disminuir</button>
    <button @click="aumentarContador" class="btn btn-primary mx-1">Aumentar</button>

    <p>Contador: {{ contador }}</p>

</template>

<script setup>
import { ref } from 'vue';

const contador = ref(0);

const aumentarContador = () => {
    contador.value++;
}

const disminuirContador = () => {

    if (contador.value > 0) {
        contador.value--;
    }

}

</script>

<style scoped></style>
