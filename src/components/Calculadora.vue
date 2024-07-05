<template>
    <div class="linha">
        <input type="number" :value="primeiroNumero" @input="updatePrimeiroNumero($event.target.value)" placeholder="Primeiro Número" />
        <select :value="operacao" @change="updateOperacao($event.target.value)">
            <option value="soma">+</option>
            <option value="subtracao">-</option>
            <option value="multiplicacao">*</option>
            <option value="divisao">/</option>
        </select>
        <input type="number" :value="segundoNumero" @input="updateSegundoNumero($event.target.value)" placeholder="Segundo Número" />
    </div>
</template>

<script setup>
import { defineEmits } from 'vue';

const props = defineProps(['primeiroNumero', 'operacao', 'segundoNumero']);

const emit = defineEmits(['update:primeiroNumero', 'update:operacao', 'update:segundoNumero']);

const updatePrimeiroNumero = (value) => {
    emit('update:primeiroNumero', value);
};

const updateOperacao = (value) => {
    emit('update:operacao', value);
};

const updateSegundoNumero = (value) => {
    emit('update:segundoNumero', value);
};
</script>

<style scoped>
.linha {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.linha input,
.linha select {
    margin: 10px;
    padding: 10px;
    font-size: 16px;
    flex: 1;
}

.linha input:first-child {
    margin-right: 5px;
}

.linha input:last-child {
    margin-left: 5px;
}
</style>