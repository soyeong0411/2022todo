<template>
  <div class="dataInput">
    <input type="text" class="inp" placeholder="할일을 입력하세요." v-model="newTodoItem">
  </div>
  <div class="btn" @click="todoItem">입력</div>
  {{newTodoItem}}
</template>

<script>
export default {
    data(){
        return {
            newTodoItem:''
        }
    },
    methods:{
        todoItem(){
            let value = this.newTodoItem;
            this.$emit("addTodo",value)
        }
    }

}
</script>

<style>

</style>