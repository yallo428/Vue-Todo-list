<template>
  <div id="app">
      <headerVue @todo = "setTodo"></headerVue>
      <contentVue v-bind:todo-data="todoData"></contentVue>
      <footerVue></footerVue>
  </div>
</template>

<script>
import vue_header from './components/todolist-header.vue'
import vue_content from './components/todolist-content.vue'
import vue_footer from './components/todolist-footer.vue'

export default {
  name: 'App',
  components: {
    'headerVue':vue_header,
    'contentVue':vue_content,
    'footerVue':vue_footer

  },
  data(){
    return{
      todoData : ""
    }
  },
  methods:{
    setTodo:function(value){
      this.todoData = value;
      console.log(value);
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
