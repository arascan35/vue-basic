<template>
    <div class="todo-item" v-bind:class="{'is-completed':todo.completed}">
        <p>
            <input type="checkbox" v-on:change="markComplete">
            {{todo.title}}
            <!-- call delItem method, todo.id is an payload -->
            <button @click="$emit('del-item',todo.id)">x</button> 
        </p>
    </div>
</template>


<script>

export default {
    name:"Todoitem",
    props:["todo"],
    methods:{
        markComplete(){
            this.todo.completed=!this.todo.completed
        }
    }
}
</script>



<style scoped>
    .todo-item{
        background: #f4f4f4;
        padding:10px;
        border-bottom:1px #ccc dotted ;
    }
    .is-completed {
        text-decoration: line-through;
    }
</style>

