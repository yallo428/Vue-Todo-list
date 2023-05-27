<template>
  <div id="hedaer">
    <h1 id="title">TodoList</h1>

    <div class="input-area">
       <input type="text" @keypress.enter="getMyTodo" v-model = 'myTodo'>
       <button v-on:click = "getMyTodo" ><img src="../assets/arrow_back_FILL0_wght400_GRAD0_opsz48.svg"></button>
      </div>
  </div>
</template>

<script>
export default {
  data(){
    return{
      myTodo: ''
    }
  },
  methods:{
    getMyTodo:function(){
      if(this.myTodo != ''){
      this.$emit('todo', this.myTodo);
      this.myTodo = ''
      }
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Nanum+Pen+Script&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Gaegu:wght@700&family=Nanum+Pen+Script&display=swap');

  #header{
    margin: 0;
  }
  #title{
    font-size:90px;
    font-family: 'Nanum Pen Script', cursive;
  }

  .input-area {
    justify-content: center;
    display: flex;
}
  .input-area>input[type="text"]{
    width: 600px;
    height: 70px;
    border: none;
    border-radius:10px;
    font-family: 'Nanum Pen Script', cursive;
    font-size:30px;
  }

  .input-area>button{
    font-size:20px;
    height: 70px;
    width: 70px;
    border: none;
    border-radius:10px;
    margin-left: -70px;
    margin-top: 1px;
    background-color: white;
    }

  .input-area>button:hover{
    background-color: gray;
  }

  .material-symbols-outlined {
  font-variation-settings:
  'FILL' 0,
  'wght' 400,
  'GRAD' 0,
  'opsz' 48
  }
</style>