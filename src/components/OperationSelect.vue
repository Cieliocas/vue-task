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

<script setup>
    import { ref, watch } from 'vue';

    const props = defineProps(['modelValue']);
    const emit = defineEmits(['update:modelValue']);

    const selectedOperation = ref(props.modelValue);

    watch(() => props.modelValue, (newValue) => {
        selectedOperation.value = newValue;
    });

    const updateValue = () => {
        emit('update:modelValue', selectedOperation.value);
    };
</script>

<style scoped>
    .operation-select {
        margin-bottom: 15px;
    }

    label {
        display: block;
        margin-bottom: 5px;
        color: #29ffc9;
    }

    select {
        width: 100%;
        padding: 8px;
        border: 1px solid #29ffc9;
        border-radius: 4px;
        background-color: #181216;
        color: white;
        font-size: 16px;
    }

    select:focus {
        outline: none;
        box-shadow: 0 0 0 2px rgba(41, 255, 201, 0.5);
    }
</style>