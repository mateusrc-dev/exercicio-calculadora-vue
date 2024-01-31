<script setup>
    const props = defineProps(['resultado']);
</script>

<template>
    <header class="p-5 mb-4 mt-2 bg-light rounded-3">
        <h2>Resultado:</h2>
        <p>
            {{ props.resultado }}
        </p>
    </header>
</template>