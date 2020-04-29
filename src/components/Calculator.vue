<template>
  <section class="calculator">
      <div class="display">{{ current }}</div>
      <button>AC</button>
      <button>+/-</button>
      <button>%</button>
      <button class="operator">÷</button>
      <button>7</button>
      <button>8</button>
      <button>9</button>
      <button class="operator">x</button>
      <button>4</button>
      <button>5</button>
      <button>6</button>
      <button class="operator">-</button>
      <button>1</button>
      <button>2</button>
      <button>3</button>
      <button class="operator">+</button>
      <button class="zero">0</button>
      <button>.</button>
      <button class="operator">=</button>
  </section >
</template>

<script>
export default {
  data () {
    return {
      current: 0
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .calculator {
    font-size: 40px;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-auto-rows: minmax(50px, auto);
    width: 30%;
    height: 10em;
    margin: auto;
    border: 2px solid black;
    border-radius: 15px;
    padding: 10px;
    box-shadow: -11px 15px 29px 0px rgba(0,0,0,0.75);
    background-color: #7CA982;
  }

  .display {
    grid-column: 1 / 5; /* start at 1 end after column 4 */
    border: 1px solid black;
    border-radius: 2px;
    margin: 10px;
    padding: 5px;
    background-color: white;
    text-align: end;
  }

  .zero {
    grid-column: 1 / 3;
  }

  button {
    font-size: 40px;
    border-radius: 10px;
    margin: 5px;
    cursor: pointer;
    background-color: rgb(202, 194, 194);
    border: 1px solid black;
    color: white;
    transition: transform 1s;
  }

  button:hover {
    background-color: #243E36;
  }

  button:active {
    background-color: #243E36;
    transform: scale(-1);
  }

  .operator {
    background-color: #C2A83E;
    color: white;
    border: 1px solid black;
  }
</style>
