<template>

    <div>
        <table class="table">
            <thead>
                <tr>
                    <th scope="col">N°</th>
                    <th scope="col">Nombre</th>
                    <th scope="col">Apellido</th>
                    <th scope="col">Edad</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(usuario, index) in usuarios" :key="index">
                    <th scope="row">{{ index + 1 }}</th>
                    <td>{{ usuario.nombre }}</td>
                    <td>{{ usuario.apellido }}</td>
                    <td>{{ usuario.edad }}</td>
                </tr>
            </tbody>
        </table>
    </div>

</template>


<script setup>

import { defineProps } from 'vue';

const props = defineProps({
    usuarios: {
        type: Array,
        required: true
    }
});

</script>

<style scoped></style>