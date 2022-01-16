<template>
  <div id="app">
    <div class="display">
    <input type="text" v-model.number="op1">
    <input type="text" v-model.number="op2"> = {{sum}}
    </div>
    <div class="keyboard">
      <button @click="plus">+</button>
      <button @click="minus">-</button>
      <button @click="multy">*</button>
      <button @click="div" v-bind:disabled="op2 === 0">/</button>
      <button @click="step">**</button>
      <button @click="int">int</button>


    </div>

  </div>
</template>

<script>
export default {
  
  data(){
    return{
      op1:0,
      op2:0,
      sum:null
    }
  },
  methods:{
    plus(){
       this.sum = this.op1 + this.op2
    },
    minus(){
       this.sum = this.op1 - this.op2
    },
    multy(){
       this.sum = this.op1 * this.op2
    },
    div(){
      if (this.op2 === 0){
         this.sum = "деление на 0 запрещено"
      }
       this.sum = this.op1 / this.op2
    },
    step(){
       this.sum = this.op1 ** this.op2
    },
    int(){
       this.sum = Math.floor((this.op1/ this.op2))
    }

    
  }
}
</script>

</script>
<style lang="scss">
#app{
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin-top: 200px;
}

</style>
