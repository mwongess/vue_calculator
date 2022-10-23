<template>
  <div class="calculator">
    <div class="output">{{}}</div>
    <div class="btn">AC</div>
    <div class="btn">+/-</div>
    <div class="btn">%</div>
    <div class="btn operator">÷</div>
    <div class="btn">7</div>
    <div class="btn">8</div>
    <div class="btn">9</div>
    <div class="btn operator">x</div>
    <div class="btn">4</div>
    <div class="btn">5</div>
    <div class="btn">6</div>
    <div class="btn operator">-</div>
    <div class="btn">1</div>
    <div class="btn">2</div>
    <div class="btn">3</div>
    <div class="btn operator">+</div>
    <div class="btn zero">0</div>
    <div class="btn">.</div>
    <div class="btn operator">=</div>
  </div>
</template>

<script>
export default {
  name: 'MyCalculator',
 
  data(){
    return{
      current: ''
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

  .calculator{
    display: grid;
    grid-template-columns: auto auto auto auto;
    grid-auto-rows: minmax(50px,auto );
    font-size: 20px;
    
  }
  .output{
    grid-column: 1/5;
    background-color: #333;
    color: #fff;
    text-align: right;
    padding: 1rem;
  }
  .zero{
    grid-column: 1/3;
  }
  .btn{
    background-color: #f2f2f2;
    border: 1px solid #999;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .operator{
    background-color: orange;
    color: #fff;
  }
</style>
