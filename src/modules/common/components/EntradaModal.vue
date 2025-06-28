<template>
    <dialog id="my_modal_1" class="modal" :open="open">
        <div class="modal-box">
            <h3 class="text-lg font-bold">Hello!</h3>
            <p class="py-4">Press ESC key or click the button below to close</p>
            <div class="modal-action flex flex-col">
                <form method="dialog" @submit.prevent="submitValue">
                    <input type="text" placeholder="Nombre del proyecto"
                        class="input input-bordered input-primary w-full flex-1" v-model="inputValue" />

                    <!-- if there is a button in form, it will close the modal -->

                    <div class="flex justify-end mt-5">
                        <button @click="$emit('close')" class="btn mr-4">Close</button>
                        <button class="btn btn-primary">Aceptar</button>
                    </div>
                </form>
            </div>
        </div>
    </dialog>
    <div v-if="open" class="modal-backdrop fixed top-0 left-0 z-10 bg-black opacity-40 w-screen h-screen">

    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

interface Props {
    open: boolean;
}

defineProps<Props>();

const emits = defineEmits<{
    close: [void];
    value: [text: string];
}>();

const inputValue = ref('');

const submitValue = () => {
    if (!inputValue.value.trim()) {

        //-----
        return;
    }
    emits('value', inputValue.value);
    emits('close');
    inputValue.value = '';

}

</script>
<style scoped></style>