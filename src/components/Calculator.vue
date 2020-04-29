<template>
  <section class="calculator">
      <div class="display">8njkfdnvjkdnvj</div>
      <div>7</div>
      <div>6</div>
      <div>5</div>
      <div>4</div>
      <div>3</div>
      <div>2</div>
      <div>1</div>
      <div>=</div>
      <div>.</div>
      <div>0</div>
  </section >
</template>

<script>
export default {
 
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .calculator {
    font-size: 40px;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-auto-rows: minmax(50px, auto);
  }

  .display {
    grid-column: 1 / 5; /* start at 1 end after column 4 */
    
  }
</style>
