<template>
  <h1>{{ msg }}</h1>
  <p>{{ count }}</p>
  <div class="grid-container">
    <div class="calculator">

      <Display v-bind:input="displayContent" />

      <input type="button" value="9" @click="handleDigit(9)">
      <input type="button" value="8" @click="handleDigit(8)">
      <input type="button" value="7" @click="handleDigit(7)">
      <input type="button" value="x" @click="handleOperation('*')" > 
      <input type="button" value="6" @click="handleDigit(6)"> 
      <input type="button" value="5" @click="handleDigit(5)">
      <input type="button" value="4" @click="handleDigit(4)">
      <input type="button" value="-" @click="handleOperation('-')">
      <input type="button" value="3" @click="handleDigit(3)">
      <input type="button" value="2" @click="handleDigit(2)">
      <input type="button" value="1" @click="handleDigit(1)">
      <input type="button" value="+" @click="handleOperation('+')">
      <input type="button" value="/" @click="handleOperation('/')"> 
      <input type="button" value="CE" @click="cleanCalculator()"> 
    <button @click="handleResult"> = </button>
  </div>
  </div>
</template>

<script>

import Display from './Display.vue';

export default {
    name: "CalculatorComp",
    components: {Display},
    props: {
        msg: String,
    },
    data() {
        return {
            displayContent: "",
            operation: "",
            digits: [],
        };
    },
    methods: {
        handleResult() {
            this.digits.push(Number(this.displayContent));
            console.log(this.operation);
            //Result method
            switch (this.operation) {
                case "+":
                    this.displayContent = this.digits[0] + this.digits[1];
                    break;
                case "-":
                    this.displayContent = this.digits[0] - this.digits[1];
                    break;
                case "*":
                    this.displayContent = this.digits[0] * this.digits[1];
                    break;
                case "/":
                    this.displayContent = this.digits[0] / this.digits[1];
                    break;
            }
        },
        handleDigit(n) {
            this.displayContent += `${n}`;
        },
        handleOperation(op) {
            this.operation = op;
            this.digits.push(Number(this.displayContent));
            this.displayContent = "";
        },
        showDisplay() {
            return this.displayContent;
        },
        cleanCalculator() {
            this.digits = [];
            this.displayContent = "";
        },
    },

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>

  .calculator{
    max-width: 200px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(4,1fr);
  }

  .calculator input, button{
    background-color: #04AA6D;
    border: none;
    color: white;
    padding: 16px;
    text-decoration: none;
    cursor: pointer;
  }

  .calculator input:hover, button:hover{
    background-color: #017d50;
  }

  .calculator button{
    grid-column: span 2;
  }

  .calculator--display{
    grid-column: 1 / -1;
    width: 100%;
    padding: 15px;
    border: 1px solid black;
    text-align: center;
    margin: 0 auto;
  }

</style>
