<template>
    <div>
        <!-- store todoitem in probs with v-bind -->
        <div v-for="todo in todos" v-bind:key="todo.id"> 
            <!-- catch button action -->
            <TodoItem v-bind:todo="todo" v-on:del-item="$emit('del-item',todo.id)"/>
        </div>
    </div>
</template>

  

<script>

import TodoItem from './Todoitem'

export default {
    name:"Todos",
    components:{
        TodoItem
    },
    props:["todos"]
}
</script>
