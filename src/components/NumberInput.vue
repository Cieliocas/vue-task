<template>
    <div class="number-input">
        <label>{{ label }}:</label>
        <input type="number" v-model="inputValue" @input="updateValue" />
    </div>
</template>

<script setup>
    import { ref, watch } from 'vue';

    const props = defineProps(['modelValue', 'label']);
    const emit = defineEmits(['update:modelValue']);

    const inputValue = ref(props.modelValue);

    watch(() => props.modelValue, (newValue) => {
        inputValue.value = newValue;
    });

    const updateValue = () => {
        emit('update:modelValue', inputValue.value);
    };
</script>

<style scoped>
.number-input {
    margin-bottom: 15px;
}

label {
    display: block;
    margin-bottom: 5px;
    color: #29ffc9;
}

input {
    width: 100%;
    padding: 10px;
    border: 1px solid #29ffc9;
    border-radius: 4px;
    background-color: #181216;
    color: white;
    font-size: 16px;
    box-sizing: border-box;
    height: 40px;
}

input:focus {
    outline: none;
    box-shadow: 0 0 0 2px rgba(41, 255, 201, 0.5);
}

.input-container {
    width: 100%;
}
</style>