<template>
    <button v-bind:class="'btn btn-circle btn-secondary fixed ' + ubicacion + ''">
        <slot />
    </button>
</template>

<script setup lang="ts">


interface Props {
    ubicacion: string;
}

withDefaults(defineProps<Props>(), {
    ubicacion: 'bottom-10 left-80',
})
</script>

<style scoped></style>