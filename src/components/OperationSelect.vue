<template>
    <div class="operation-select">
        <label>Operação:</label>
        <select v-model="selectedOperation" @change="updateValue">
            <option value="+">Adição (+)</option>
            <option value="-">Subtração (-)</option>
            <option value="*">Multiplicação (*)</option>
            <option value="/">Divisão (/)</option>
        </select>
    </div>
</template>

<script>

</script>