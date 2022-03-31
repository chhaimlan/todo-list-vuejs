<template>
<div>
  <Apptodo v-on:add-todo="addTodo"/>
  <Todos v-on:delete-todo="deleteTodo" v-bind:todos="todos"/>
</div>
</template>

<script>
import Apptodo from './components/Apptodo.vue'
import Todos from './components/Todos.vue'

export default {
  name: 'App',
  components: {
   Apptodo,
   Todos,
  },
  data(){
    return {
      todos:[
        {
          id:'1',
          title:'My task Learn vue',
          completed: false
        },
         {
          id:'2',
          title:'Then convert html to vue',
          completed: false
        },
         {
          id:'3',
          title:'Learning project code and laravel',
          completed: false
        },
         {
          id:'4',
          title:'Learn react Js',
          completed: false
        },
         {
          id:'5',
          title:'Improve my English',
          completed: false
        }
      ]
    }
  },
  methods:{
    addTodo(todo){
      //adding todo array
       this.todos = [...this.todos,todo]
    },
    deleteTodo(id){
      this.todos = this.todos.filter((todo) => todo.id !== id)
    }
  }
}
</script>

<style>

</style>
