<script setup>
import { reactive, watchEffect } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Calculadora from './components/Calculadora.vue';


const estado = reactive ({
  primeiroNumero: 0,
  operacao: 'soma',
  segundoNumero: 0,
  resultado: 0
});

watchEffect( () => {
  const num1 = parseFloat(estado.primeiroNumero) || 0;
  const num2 = parseFloat(estado.segundoNumero) || 0;

  switch (estado.operacao) {
    case 'soma':
      estado.resultado = num1 + num2;
      break;
    case 'subtracao':
      estado.resultado = num1 - num2;
      break;
    case 'multiplicacao':
      estado.resultado = num1 * num2;
      break;
    case 'divisao':
      estado.resultado = num2 !== 0 ? num1 / num2: 'Erro';
      break;
    default:
      estado.resultado = 0;
    }
});
</script>

<template>
  <div class="container">
    <Cabecalho :resultado= "estado.resultado" />
    <Calculadora
    v-model:primeiroNumero="estado.primeiroNumero"
    v-model:operacao="estado.operacao"
    v-model:segundoNumero="estado.segundoNumero"
    />
  </div>
</template>

<style scoped>
.container {
  max-width: 600px;
  margin: auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}
</style>
