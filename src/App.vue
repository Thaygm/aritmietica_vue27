<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Operacao from './components/Operacao.vue';
import Resultado from './components/Resultado.vue';

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
      <Cabecalho />
      <Operacao :operacao="evento=> estado.operation = evento.target.value" :numero1="evento => estado.numero1 = evento.target.value" :numero2="evento => estado.numero2 = evento.target.value"></Operacao>
      <Resultado :numero1="estado.numero1" :numero2="estado.numero2" :result="resultado()"/>
    </div>
  </body>
</template>

<style>
</style>