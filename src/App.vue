<script setup>
import { reactive } from 'vue';
import cabecalho from './components/cabecalho.vue';
import operacao from './components/operacao.vue';
import resultado from './components/resultado.vue';

const estado = reactive({
  operation: '+',
  numero1: '',
  numero2: ''
})

const resultado = ()=> {
  const {operation} = estado;
  switch (operation) {
    case'-':
    return parseFloat(estado.numero1) - parseFloat(estado.numero2);
    case'*':
    return parseFloat(estado.numero1) * parseFloat(estado.numero2);
    case'/':
    return parseFloat(estado.numero1) / parseFloat(estado.numero2);
    default:
    return parseFloat(estado.numero1) + parseFloat(estado.numero2);
  }
}
</script>

<template>
  <body>
    <div class="container">
      <cabecalho />
      <operacao :operacao="evento=> estado.operation = evento.target.value" :numero1="evento => estado.numero1 = evento.target.value" :numero2="evento => estado.numero2 = evento.target.value"></operacao>
    </div>
  </body>
</template>

<style>
</style>