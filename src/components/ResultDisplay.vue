<template>
    <div class="result-display">
        <h2>Resultado:</h2>
        <p>{{ result }}</p>
    </div>
</template>

<script setup>
defineProps(['result']);
</script>

<style scoped>
.result-display {
    margin-top: 20px;
    text-align: center;
}

h2 {
    color: #29ffc9;
}

p {
    font-size: 24px;
    font-weight: bold;
    color: white;
}
</style>