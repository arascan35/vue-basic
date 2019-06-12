<template>
  <div id="app">
     <!-- store todos in probs with v-bind -->
   <Todos v-bind:todos="todos" v-on:del-item="deleteItem"/>

  </div>
</template>

<script>

import Todos from './components/Todos'

export default {
  name: 'app',
  components: {
    Todos
  },
  data(){
    return {
      todos:[
        {
          id:1,
          title:"Todo-1",
          completed:false
        },
                {
          id:2,
          title:"Todo-2",
          completed:true
        },
                {
          id:3,
          title:"Todo-3",
          completed:false
        },
                {
          id:4,
          title:"Todo-4",
          completed:true
        },
                {
          id:5,
          title:"Todo-5",
          completed:false
        },
      ]
    }
  },
    methods:{
    deleteItem(id){
      this.todos=this.todos.filter(todo=>todo.id !== id)
    }
  }
}
</script>

<style>

</style>
