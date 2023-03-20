<template>
  <h1>{{ msg }}</h1>
  <p>{{ count }}</p>
  <div class="grid-container">
    <p> {{ display }}</p> <br>
    <input type="submit" value="1" @click="handleDigit(1)">
    <input type="submit" value="2" @click="handleDigit(2)">
    <input type="submit" value="3" @click="handleDigit(3)"> <br>
    <input type="submit" value="4" @click="handleDigit(4)">
    <input type="submit" value="5" @click="handleDigit(5)">
    <input type="submit" value="6" @click="handleDigit(6)"> <br>
    <input type="submit" value="7" @click="handleDigit(7)">
    <input type="submit" value="8" @click="handleDigit(8)">
    <input type="submit" value="9" @click="handleDigit(9)"> <br>
    <input type="submit" value="+" @click="handleOperation('+')"> 
    <input type="submit" value="-" @click="handleOperation('-')"> 
    <input type="submit" value="x" @click="handleOperation('*')"> 
    <input type="submit" value="/" @click="handleOperation('/')"> 
    <input type="submit" value="CE" @click="cleanCalculator()"> 
    <button @click="handleResult"> = </button>
  </div>
</template>

<script>

export default {
  name: 'CalculatorComp',

  props: {
    msg: String
  },

  data() {
    return {
      display: "",
      operation: "",
      digits: [],
    }
  },

  methods: {
    handleResult(){
      this.digits.push(Number(this.display))
      console.log(this.operation);

      //Result method
      switch (this.operation) {
        case "+":
          this.display = this.digits[0] + this.digits[1]
          break;
        case "-":
          this.display = this.digits[0] - this.digits[1]
          break;
        case "*":
          this.display = this.digits[0] * this.digits[1]
          break;
        case "/":
          this.display = this.digits[0] / this.digits[1]
          break;
      }
       
    },

    handleDigit(n){
      this.display += n
    },

    handleOperation(op){
      this.operation = op
      this.digits.push(Number(this.display))
      this.display = ""
    },

    showDisplay(){
      return this.display
    },

    cleanCalculator(){
      this.digits = []
      this.display = 0
    }

  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
