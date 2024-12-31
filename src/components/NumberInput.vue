<template>
    <div class="number-input">
        <label>{{ label }}:</label>
        <input type="number" v-model="inputValue" @input="updateValue" />
    </div>
</template>

<script>
.number-input {
    margin-bottom: 15px;
}
</script>