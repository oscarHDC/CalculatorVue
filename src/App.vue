<template>
  <CalculatorComp msg="Welcome to Your Vue.js App"/>
</template>

<script>
import CalculatorComp from './components/Calculator.vue'

export default {
  name: 'App',
  components: {
    CalculatorComp
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
