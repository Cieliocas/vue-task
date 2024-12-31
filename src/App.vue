<script setup>
// import { ref, computed } from 'vue';
import NumberInput from './components/NumberInput.vue';
// import OperationSelect from './components/OperationSelect.vue';
import ResultDisplay from './components/ResultDisplay.vue';

const number1 = ref(0);
const number2 = ref(0);
const operation = ref('+');

const result = computed(() => {
	const num1 = parseFloat(number1.value);
	const num2 = parseFloat(number2.value);

	switch (operation.value) {
		case '+':
			return num1 + num2;
		case '-':
			return num1 - num2;
		case '*':
			return num1 * num2;
		case '/':
			return num2 !== 0 ? num1 / num2 : 'Erro: Divisão por zero';
		default:
			return 'Operação inválida';
	}
});
</script>

<template>
	<div class="calculator-container">
		<div class="calculator-window">
			<h1>Calculadora Aritmética</h1>
			<NumberInput v-model="number1" label="Número 1" />
			<NumberInput v-model="number2" label="Número 2" />
			<OperationSelect v-model="operation" />
			<ResultDisplay :result="result" />
		</div>
	</div>
</template>

<style scoped>
body {
	margin: 0;
	padding: 0;
	background-color: #392a35;
	color: white;
	font-family: Arial, sans-serif;
}
</style>
