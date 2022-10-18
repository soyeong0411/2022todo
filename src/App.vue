<template>
  <div class="hea">
    <h1>Todo List</h1>
  </div>
  <TodoInput @addTodo="addTodoItem"></TodoInput>
  <Todolist :todoItem="todoItem" @reDel="removeDel"></Todolist>
  <TodoFooter @clearAll="clearAll"></TodoFooter>
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
    created(){
      for(let i=0;i<localStorage.length;i++){
        this.todoItem.push(localStorage.key(i))
      }
    },
    methods : {
      addTodoItem(item){
        this.todoItem.push(item)
        localStorage.setItem(item,item)
      },
      removeDel(num,item){
        this.todoItem.splice(num,1)
        localStorage.removeItem(item)
        
      },
      clearAll(){
        localStorage.clear();
        this.todoItem=[];
      },
    }
    
}
</script>

<style>

</style>