<template>
    <div class="overflow-x-auto w-full">
        <table class="table">
            <!-- head -->
            <thead>
                <tr>
                    <th></th>
                    <th>Proyecto</th>
                    <th>Tareas</th>
                    <th>Avance</th>
                </tr>
            </thead>
            <tbody>
                <!-- row 1 -->
                <tr>
                    <th>1</th>
                    <td>Cy Ganderton</td>
                    <td>Quality Control Specialist</td>
                    <td>Blue</td>
                </tr>

            </tbody>
        </table>
        <boton-flotante>
            <add-button></add-button>
        </boton-flotante>

    </div>
</template>

<script setup lang="ts">
import BotonFlotante from '@/modules/common/components/BotonFlotante.vue';
import AddButton from '@/modules/common/icons/AddButton.vue';
</script>

<style scoped></style>