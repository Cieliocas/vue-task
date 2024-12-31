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
    color: #ffffff;
    font-weight: lighter;
    font-size: 12px;
}

input {
    width: 100%;
    padding: 10px;
    border: 1px solid #414141;
    border-radius: 8px;
    background-color: transparent;
    color: #fff;
    box-sizing: border-box;
    height: 40px;
}

input:focus {
    outline: none;
    border-color: #e81cff;
}

.input-container {
    width: 100%;
}
</style>