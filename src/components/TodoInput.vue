<template>
  <div class="dataInput">
    <input type="text" class="inp" placeholder="할일을 입력하세요." v-model="newTodoItem">
  </div>
  <div class="btn" @click="todoItem">입력</div>
  {{newTodoItem}}


  <transition name="mView">
  <Modal v-if="modal" @click="modal=false">
    <template v-slot:header>경고</template>
    <template v-slot:body>자료를 입력하세요.</template>
  </Modal>
  </transition>
</template>

<script>
import Modal from "@/components/Modal.vue"


export default {
    components:{Modal,},

    data(){
        return {
            newTodoItem:'',
            modal:false,
        }
    },
    methods:{
        todoItem(){
            if( this.newTodoItem != ''){
                
                let value = this.newTodoItem && this.newTodoItem.trim();
                this.$emit("addTodo",value)
            }else{
                //alert("할일을 입력하세요.")
                this.modal = true
            }
            this.newTodoItem=""
        }
    }

}
</script>

<style>

.mView-enter-from{opacity: 0;transform: translate(-50%,100%);}
.mView-enter-active{transition:0.3s;}
.mView-enter-to{opacity: 1;transform: translate(-50%,0);}

.mView-leave-from{opacity: 1;}
.mView-leave-active{transition:0.3s;}
.mView-leave-to{opacity: 0;}

</style>