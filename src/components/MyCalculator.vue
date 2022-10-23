<template>
  <div class="calculator">
    <div class="output">{{current || '0'}}</div>
    <div @click="clear" class="btn">AC</div>
    <div @click="sign" class="btn">+/-</div>
    <div @click="percent" class="btn">%</div>
    <div @click="append()" class="btn operator">÷</div>
    <div @click="append()" class="btn">7</div>
    <div @click="append()" class="btn">8</div>
    <div @click="append()" class="btn">9</div>
    <div @click="append()" class="btn operator">x</div>
    <div @click="append()" class="btn">4</div>
    <div @click="append()" class="btn">5</div>
    <div @click="append()" class="btn">6</div>
    <div @click="append()" class="btn operator">-</div>
    <div @click="append()" class="btn">1</div>
    <div @click="append()" class="btn">2</div>
    <div @click="append()" class="btn">3</div>
    <div @click="append()" class="btn operator">+</div>
    <div @click="append()" class="btn zero">0</div>
    <div @click="append()" class="btn">.</div>
    <div @click="append()" class="btn operator">=</div>
  </div>
</template>

<script>
export default {
  name: 'MyCalculator',
 
  data(){
    return{
      current: '123'
    }
  },
  methods: {
    clear(){
      this.current = ""
    },
    sign(){
      this.current = this.current.charAt(0) === '-' ? this.current.slice(1) : `-${this.current}`
    },
    percent(){
      this.current = `${parseFloat(this.current) / 100}`
    },
    append(){

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
