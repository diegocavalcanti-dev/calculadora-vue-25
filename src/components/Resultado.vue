<script setup>
const props = defineProps(['resultado']);
</script>

<template>
    <div class="mt-3 btn btn-primary">
        <h2>Resultado: {{ props.resultado }}</h2>
    </div>
</template>
