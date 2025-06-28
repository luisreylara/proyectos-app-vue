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

        <CustomModal :open="refCustomModal">
            <template #cabecera>
                <div>
                    <h3 class="text-lg font-bold">Titulo2</h3>
                    <p class="py-4">Subtitulo2</p>
                </div>
            </template>

            <template #acciones>
                <div>
                    <button @click="refCustomModal = false" class="btn">Boton 1</button>
                    <button @click="refCustomModal = false" class="btn">Boton 2</button>
                </div>
            </template>

        </CustomModal>

        <EntradaModal :open="refEntradaModal" @close="refEntradaModal = false" @value="nuevoProyecto">

        </EntradaModal>


        <BotonFlotante @click=" refEntradaModal = true" ubicacion="bottom-10 left-80">
            <AddButton></AddButton>
        </BotonFlotante>

        <BotonFlotante @click=" refCustomModal = true" ubicacion="bottom-10 right-80">
            <ModalIcon></ModalIcon>
        </BotonFlotante>
    </div>
</template>

<script setup lang="ts">
import BotonFlotante from '@/modules/common/components/BotonFlotante.vue';
import AddButton from '@/modules/common/icons/AddButton.vue';
import ModalIcon from '@/modules/common/icons/ModalIcon.vue';
import CustomModal from '@/modules/common/components/CustomModal.vue';
import EntradaModal from '@/modules/common/components/EntradaModal.vue';
import { ref } from 'vue';

const refCustomModal = ref(false);
const refEntradaModal = ref(false);

const nuevoProyecto = (miNuevoProyecto: string) => {
    console.log(miNuevoProyecto);
}

</script>

<style scoped></style>