<template>
 <div id="app">
    <h2>Calculadora VUE</h2>

    <div>
      <label for="number1">Número 1:</label>
      <input type="number" id="number1" v-model="number1">
    </div>

    <div>
      <label for="number2">Número 2:</label>
      <input type="number" id="number2" v-model="number2">
    </div>

    <div>
      <label for="operation">Operação:</label>
      <select id="operation" v-model="selectedOperation">
        <option value="add">Soma (+)</option>
        <option value="subtract">Subtração (-)</option>
        <option value="multiply">Multiplicação (*)</option>
        <option value="divide">Divisão (/)</option>
      </select>
    </div>

    <div>
      <button @click="calculate">Calcular</button>
    </div>

    <div>
      <label for="result">Resultado:</label>
      <input type="text" id="result" v-model="result" readonly>
    </div>
  </div>
</template>

<script>
new Vue({
      el: '#app',
      data: {
        number1: 0,
        number2: 0,
        selectedOperation: 'add',
        result: ''
      },
      methods: {
        calculate() {
          switch (this.selectedOperation) {
            case 'add':
              this.result = this.number1 + this.number2;
              break;
            case 'subtract':
              this.result = this.number1 - this.number2;
              break;
            case 'multiply':
              this.result = this.number1 * this.number2;
              break;
            case 'divide':
              this.result = this.number1 / this.number2;
              break;
            default:
              this.result = '';
          }
        }
      }
    });
</script>

<style>

</style>