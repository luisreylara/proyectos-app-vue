<template>
    <dialog class="modal" :open="open">
        <div class="modal-box">

            <slot name="cabecera" />

            <slot name="acciones" />

        </div>
    </dialog>
    <div v-if="open" class="modal-backdrop fixed top-0 left-0 z-10 bg-black opacity-40 w-scrren h-screen">

    </div>
</template>

<script setup lang="ts">
interface Props {
    open?: boolean;
}

withDefaults(defineProps<Props>(), {
    open: false,
})

</script>

<style scoped></style>