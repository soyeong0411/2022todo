<template>
  <div class="dataInput">
    <input type="text" class="inp" placeholder="할일을 입력하세요." v-model="newTodoItem">
    <div class="btn" @click="todoItem">입력</div>
  </div>
  
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

<style lang="scss">

.dataInput{
    display: flex;
    gap: 15px;
    margin-top: 15px;
    .inp{
        flex:1 0 auto;
        height: 38px;
        border-radius: 10px;
        border: 2px solid rgb(93, 50, 8);
        text-indent: 10px;
        background: rgb(235, 225, 211);
        font-size: 17px;
        &:focus{
           outline: none;
        }
    }
}


.mView-enter-from{opacity: 0;transform: translate(-50%,100%);}
.mView-enter-active{transition:0.3s;}
.mView-enter-to{opacity: 1;transform: translate(-50%,0);}

.mView-leave-from{opacity: 1;}
.mView-leave-active{transition:0.3s;}
.mView-leave-to{opacity: 0;}

</style>