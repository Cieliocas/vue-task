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
</style>