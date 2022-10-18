<template>
  <div class="hea">
    <h1>Todo List</h1>
  </div>
  <TodoInput @addTodo="addTodoItem"></TodoInput>
  <Todolist :todoItem="todoItem"></Todolist>
  <TodoFooter></TodoFooter>
</template>

<script>
import TodoInput from './components/TodoInput.vue';
import Todolist from './components/Todolist.vue';
import TodoFooter from './components/TodoFooter.vue';
export default {
    components: { Todolist, TodoInput, TodoFooter },
    data(){
      return {
        todoItem:[]
      }
    },
    methods : {
      addTodoItem(item){
        this.todoItem.push(item)
      }
    }
    
}
</script>

<style>

</style>