<template>
  <div id="content">
    <ul>
      <li v-for = "(todolist, index) in todolists" v-bind:key="index">
        {{todolist}}
      </li>

    </ul>
  </div>
</template>

<script>
export default {
  data(){
    return{
      todolists:[]
    }
  },
  props:['todoData'],
  watch:{
    todoData:function(){
      this.todolists.push(this.todoData);
    }
  }
}
</script>

<style>

</style>