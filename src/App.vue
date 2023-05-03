<template>
  <div class="calculator">
    <div class="screen">{{ display }}</div>
    <div class="buttons">
      <button v-for="button in buttons" :key="button" @click="handleClick(button)">{{ button }}</button>
      <button @click="calculate()">=</button>
      <button @click="clear()">C</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      display: "",
      buttons: ["1", "2", "3", "-", "4", "5", "6", "+", "7", "8", "9", "*", "0", ".", "%", "/", "√"],
    };
  },
  methods: {
    handleClick(button) {
      this.display += button;
    },
    calculate() {
      try {
        this.display = eval(this.display).toString();
      } catch (error) {
        this.display = "";
      }
    },
    clear() {
      this.display = "";
    },
  },
};
</script>

<style>
.calculator {
  width: 300px;
  margin: auto;
  border: 1px solid #19A7CE;
  border-radius: 10px;
  padding: 10px;
  box-shadow: 0px 0px 5px 0px #19A7CE;
}

.screen {
  height: 50px;
  margin-bottom: 10px;
  background-color: #FEFF86;
  border: 1px solid #19A7CE;
  border-radius: 10px;
  padding: 10px;
  font-size: 24px;
  text-align: right;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 10px;
  background-color: #146C94;
}

button {
  height: 50px;
  background-color: #B0DAFF;
  border: none;
  border-radius: 10px;
  font-size: 24px;
  cursor: pointer;
}

button:hover {
  background-color: #19A7CE;
}
</style>