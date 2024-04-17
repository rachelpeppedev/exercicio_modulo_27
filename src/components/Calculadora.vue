<script setup>
const props = defineProps(['primeiroNumero', 'operacao', 'segundoNumero'])
</script>
<template>
    <div class="container mt-2 p-2 bg-dark rounded-3 d-flex justify-content-center">
        <input type="number" v-model.number="$props.primeiroNumero">
        <select v-model="$props.operacao">
            <option value="soma">+</option>
            <option value="subtracao">-</option>
            <option value="multiplicacao">*</option>
            <option value="divisao">/</option>
        </select>
        <input type="number" v-model.number="$props.segundoNumero">
    </div>
</template>