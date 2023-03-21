<template>
  <h1>{{ msg }}</h1>
  <p>{{ count }}</p>
  <div class="grid-container">
    <div class="calculator">
      <Display v-bind:input="displayContent" />
      <KeyBoard @key-Clicked="handleClick" />
  </div>
  </div>
</template>

<script>

import Display from './Display.vue';
import KeyBoard from './KeyBoard.vue';

export default {
    name: "CalculatorComp",
    components: {Display, KeyBoard},
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

        handleClick(value){
            //Funcionalidad botones
            console.log( value);
            switch (value) {
              case "x":
              case "-":
              case "/":
              case "+":
                this.handleOperation(value);
                break;
              case "CE":
                this.cleanCalculator();
                break;
              case "=":
                this.handleResult()  
                break;  
            
              default:
                this.handleDigit(value)
                break;
            }

        }
    },
    

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>

  .calculator{
    max-width: 250px;
    margin: 0 auto;
    
  }


</style>
