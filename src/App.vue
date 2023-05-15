<template>
 <div id="app">
    <h2>Calculadora VUE</h2>

    <div>
      <label for="numero1">Número 1:</label>
      <input type="numero" id="numero1" v-model="numero1">
    </div>

    <div>
      <label for="numero2">Número 2:</label>
      <input type="numero" id="numero2" v-model="numero2">
    </div>

    <div>
      <label for="operacao">Operação:</label>
      <select id="operacao" v-model="selectedoperacao">
        <option value="add">Somar </option>
        <option value="subtract">Subtrair </option>
        <option value="multiply">Multiplicar </option>
        <option value="divide">Dividir </option>
      </select>
    </div>

    <div>
      <button @click="calcular">Calcular</button>
    </div>

    <div>
      <label for="resultado">Resultado:</label>
      <input type="text" id="result" v-model="result" readonly>
    </div>
  </div>
</template>

<script>
new Vue({
      el: '#app',
      data: {
        numero1: 0,
        numero2: 0,
        selectedOperation: 'add',
        result: ''
      },
      methods: {
        calculate() {
          switch (this.selectedOperation) {
            case 'add':
              this.result = this.numero1 + this.numero2;
              break;
            case 'subtract':
              this.result = this.numero1 - this.numero2;
              break;
            case 'multiply':
              this.result = this.numero1 * this.numero2;
              break;
            case 'divide':
              this.result = this.numero1 / this.numero2;
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