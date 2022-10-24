<template>
  <div class="calculator">
    <div class="output">{{current || '0'}}</div>
    <div @click="clear" class="btn">AC</div>
    <div @click="sign" class="btn">+/-</div>
    <div @click="percent" class="btn">%</div>
    <div @click="divide()" class="btn operator">÷</div>
    <div @click="append(7)" class="btn">7</div>
    <div @click="append(8)" class="btn">8</div>
    <div @click="append(9)" class="btn">9</div>
    <div @click="times" class="btn operator">x</div>
    <div @click="append(4)" class="btn">4</div>
    <div @click="append(5)" class="btn">5</div>
    <div @click="append(6)" class="btn">6</div>
    <div @click="minus" class="btn operator">-</div>
    <div @click="append(1)" class="btn">1</div>
    <div @click="append(2)" class="btn">2</div>
    <div @click="append(3)" class="btn">3</div>
    <div @click="plus" class="btn operator">+</div>
    <div @click="append(0)" class="btn zero">0</div>
    <div @click="dot()" class="btn">.</div>
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
    append(number){
      this.current = `${this.current}${number}`
    },
    times(){

    },
    divide(){

    },
    minus(){},
    dot(){
      if(this.current.indexOf('.') === -1 ){
        this.append(".")
      }
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
