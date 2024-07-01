<script setup>
import { reactive, watchEffect } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Calculadora from './components/Calculadora.vue';


const estado = reactive ({
  primeiroNumero: '',
  operacao: 'soma',
  segundoNumero: '',
  resultado: ''
});

watchEffect( () => {
  switch (estado.operacao) {
    case 'soma':
      estado.resultado = estado.primeiroNumero + estado.segundoNumero;
      break;
    case 'subtracao':
      estado.resultado = estado.primeiroNumero - estado.segundoNumero;
      break;
    case 'multiplicacao':
      estado.resultado = estado.primeiroNumero * estado.segundoNumero;
      break;
    case 'divisao':
      estado.resultado = estado.primeiroNumero / estado.segundoNumero;
      break;
    default:
      estado.resultado = 0;
    }
});
</script>

<template>
  <div class="container">
    <Cabecalho: estado.resultado = "resultado()" />
    <Calculadora: estado.resultado = "estado.resultado = estado.primeiroNumero + estado.segundoNumero"/>
  </div>
</template>

<style scoped>
.container {
  max-width: 500px;
}
</style>
