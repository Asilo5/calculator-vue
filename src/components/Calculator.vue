<template>
  <section class="calculator">
      <div class="display">{{ current || '0' }}</div>
      <button @click="clear">AC</button>
      <button @click="sign">+/-</button>
      <button @click="percent">%</button>
      <button @click="divide" class="operator">÷</button>
      <button @click="append('7')">7</button>
      <button @click="append('8')">8</button>
      <button @click="append('9')">9</button>
      <button @click="times" class="operator">x</button>
      <button @click="append('4')">4</button>
      <button @click="append('5')">5</button>
      <button @click="append('6')">6</button>
      <button @click="minus" class="operator">-</button>
      <button @click="append('1')">1</button>
      <button @click="append('2')">2</button>
      <button @click="append('3')">3</button>
      <button @click="add" class="operator">+</button>
      <button @click="append('0')" class="zero">0</button>
      <button @click="dot">.</button>
      <button @click="equal" class="operator">=</button>
  </section >
</template>

<script>
export default {
  data () {
    return {
      current: '',
      previous: null,
      operator: null,
      operatorClicked: false
    }
  },
  methods : {
    clear () {
      this.current = '';
    },

    sign () {
      this.current = this.current.charAt(0) === '-' ? this.current.slice(1) : `-${this.current}`;
    },

    percent () {
       this.current = `${parseFloat(this.current) / 100}`;
    },

    append (number) {
      if(this.operatorClicked) {
        this.current = '';
        this.operatorClicked = false;
      }
       this.current = `${this.current}${number}`;
    },

    dot () {
      if(this.current.indexOf('.') === -1) {
         this.append('.'); 
      }
    },

    setPrevious () {
       this.previous = this.current;
       this.operatorClicked = true;
    },

    divide () {
       this.operator = (a, b) => a / b * 100;
       this.setPrevious();
    },

    times () {
       this.operator = (a, b) => a * b;
       this.setPrevious();
    },

    add () {
       this.operator = (a, b) => a + b;
       this.setPrevious();
    },

    minus () {
       this.operator = (a, b) => a - b;
       this.setPrevious();
    },

    equal () {
      this.current = `${this.operator(parseFloat(this.current), parseFloat(this.previous))}`;
      this.previous = null;
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
    overflow: auto;
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
