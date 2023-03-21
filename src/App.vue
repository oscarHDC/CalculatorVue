<template>
  <CalculatorComp msg="Calculadora Vue"/>
</template>

<script>
import CalculatorComp from './components/Calculator.vue'

export default {
  name: 'App',
  components: {
    CalculatorComp,
}
}
</script>

<style>

*{
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
