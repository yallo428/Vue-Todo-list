<template>
  <div id="hedaer">
    <h1 id="title">TodoList</h1>

    <div class="input-area">
       <input type="text" style = "width:400px;font-size:20px" v-model = 'myTodo'>
       <button v-on:click = "getMyTodo">입력</button>
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
      this.$emit('todo', this.myTodo);
    }
  }
}
</script>

<style>
</style>