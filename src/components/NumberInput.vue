<template>
    <div class="number-input">
        <label>{{ label }}:</label>
        <input type="number" v-model="inputValue" @input="updateValue" />
    </div>
</template>

<script>
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
    padding: 8px;
    border: 1px solid #29ffc9;
    border-radius: 4px;
    background-color: #392a35;
    color: white;
    font-size: 16px;
}

input:focus {
    outline: none;
    box-shadow: 0 0 0 2px rgba(41, 255, 201, 0.5);
}
</style>