<template>
    <h1 class="text-center">Ejemplo formulario con Vue</h1>

    <div>
        <form class="w-50 mx-auto" @submit.prevent="registrarUsuario">
            <div class="mb-3">
                <label for="nombre" class="form-label">Nombre:</label>
                <input type="text" name="nombre" id="nombre" class="form-control" required autocomplete="off"
                    v-model="nuevoUsuario.nombre">
            </div>
            <div class="mb-3">
                <label for="apellido" class="form-label">Apellido:</label>
                <input type="text" name="apellido" id="apellido" class="form-control" required autocomplete="off"
                    v-model="nuevoUsuario.apellido">
            </div>
            <div class="mb-3">
                <label for="edad" class="form-label">Edad</label>
                <input type="number" name="edad" id="edad" class="form-control" min="0" required autocomplete="off"
                    v-model="nuevoUsuario.edad">
            </div>
            <div class="mb-3">
                <input type="submit" value="Registrar" class="btn btn-primary">
            </div>
        </form>
    </div>

    <!-- AQUÍ AGREGAMOS EL COMPONENTE TABLEUSERS -->

    <TableUsers v-if="usuarios.length" :usuarios="usuarios" />
    <h3 class="text-center" v-else>Sin usuarios por mostrar</h3>

</template>

<script setup>

import { ref } from 'vue';

//AQUÍ IMPORTAMOS LOS COMPONENTES

import TableUsers from '@/components/TableUsers.vue';

const usuarios = ref([]);

const nuevoUsuario = ref({
    nombre: "",
    apellido: "",
    edad: 0
});

const registrarUsuario = () => {
    usuarios.value.push({ ...nuevoUsuario.value });

    nuevoUsuario.value = { nombre: "", apellido: "", edad: 0 };
}


</script>


<style scoped></style>