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

<script setup>
	import { ref, computed } from 'vue';
	import NumberInput from './components/NumberInput.vue';
	import OperationSelect from './components/OperationSelect.vue';
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

<style>
	body {
		margin: 0;
		padding: 0;
		background-color: #212121;
		color: #FAFAFA;
		font-family: "Roboto", serif;
	}

	.calculator-container {
		display: flex;
		justify-content: center;
		align-items: center;
		height: 100vh;
	}

	.calculator-window {
		background: linear-gradient(#212121, #212121) padding-box,
		linear-gradient(145deg, transparent 35%,#e81cff, #29ffc9) border-box;
		border-radius: 10px;
		padding: 20px;
		max-width: 350px;
		width: 100%;
		border: 2px solid transparent;
		font-size: 14px;
		color: white;
		flex-direction: column;
		box-sizing: border-box;
	}

	h1 {
		text-align: center;
		margin-bottom: 20px;
		font-weight: lighter;
		background-color: #f3ec78;
		background-image: linear-gradient(45deg, #e81cff, #29ffc9);
		background-size: 100%;
		-webkit-background-clip: text;
		-moz-background-clip: text;
		-webkit-text-fill-color: transparent; 
		-moz-text-fill-color: transparent;
	}
</style>