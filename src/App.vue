<template>
  <section id="app">
    <Calculator msg="Welcome to Your Vue.js App"/>
  </section>
</template>

<script>
import Calculator from './components/Calculator.vue'

export default {
  name: 'App',
  components: {
    Calculator
  }
}
</script>

<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    margin-top: 12em;
  }

 * {
    box-sizing: border-box;
    padding: 0;
    margin: 0;
  }

  body {
    background-color: #E0EEC6;
  }

</style>
