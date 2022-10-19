<template>
  <div class="header">
    <h1>ToDoList</h1>
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

<style lang="scss">
@import url(./assets/style.css);
@import url('https://fonts.googleapis.com/css2?family=IBM+Plex+Sans+KR:wght@400;500;600;700&display=swap');

body{font-family: 'IBM Plex Sans KR', sans-serif;}

#app{
  width: 420px;
  margin: 0 auto;
  background-image: url(./assets/bg.jpg);
  padding: 30px 40px;
  .header{
    text-align: center;
    color:rgb(61, 46, 29);
    font-size: 22px;
  }
}

</style>