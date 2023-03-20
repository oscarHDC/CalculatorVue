<template>
  <h1>{{ msg }}</h1>
  <p>{{ count }}</p>
  <div class="grid-container">
    <p> {{ display }}</p> <br>
    <input type="submit" value="1" @click="handleClick(1)">
    <input type="submit" value="2" @click="handleClick(2)">
    <input type="submit" value="3" @click="handleClick(3)"> <br>
    <input type="submit" value="4" @click="handleClick(4)">
    <input type="submit" value="5" @click="handleClick(5)">
    <input type="submit" value="6" @click="handleClick(6)"> <br>
    <input type="submit" value="7" @click="handleClick(7)">
    <input type="submit" value="8" @click="handleClick(8)">
    <input type="submit" value="9" @click="handleClick(9)"> <br>
    <input type="submit" value="+" @click="handleOperation('+')"> 
    <input type="submit" value="-" @click="handleOperation('+')"> 
    <input type="submit" value="*" @click="handleOperation('+')"> 
    <input type="submit" value="/" @click="handleOperation('+')"> 
    <button @click="handleButton"> = </button>
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
    handleButton(){
      this.digits.push(Number(this.display))
      this.display = this.digits.reduce((digit, acc) => acc += Number(digit), 0)
    },

    handleClick(n){
      this.display += n
    },

    handleOperation(){
      this.digits.push(Number(this.display))
      this.display = ""
    },

    showDisplay(){
      return this.display
    },

  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
