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
    background: -webkit-linear-gradient(#fa02ee, #00cf9f);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

p {
    font-size: 24px;
    font-weight: lighter;
    color: white;
}
</style>