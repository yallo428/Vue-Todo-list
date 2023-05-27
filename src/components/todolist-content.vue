<template>
  <div id="content">
    <ul>
      <li class = "list" v-for = "(todoDatas, index) in todoDatas" v-bind:key="index">
        <p>{{todoDatas}}</p>
        <button @click = "removeTodo(index)">삭제</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data(){
    return{
      todoDatas : this.todoData
    }
  },
  props:{todoData:Array},
  methods:{
    removeTodo:function(index){
      this.todoDatas.splice(index, 1);
      console.log(index);
      this.$emit('remove', this.todoDatas);
    }
  },
}
</script>
<style>
  ul{
    margin:0;
    padding: 0;
    display: inline-block;
    list-style-type: none;

  }
    .list{
      width: 700px;
      height: 70px;
      background-color:white;
      margin-top: 10px; 
      border-radius: 10px;
    }
</style>