<template>
  <ul>
    <li v-for="(item,i) in todoItem" :key="i" class="itemList">
        <div class="list">
            <i class="fa-regular fa-square-check"></i>{{item}}
        </div>
        
        <div class="del" @click="removeDel(i,item)" >
            <i class="fa-solid fa-eraser"></i>
        </div>

    </li>

        
    
  </ul>
</template>

<script>
export default {
    props : [
        "todoItem"
    ],
    methods:{
        removeDel(num,item){
            this.$emit("reDel",num,item) // 함수, 인자값
        }
    }
}
</script>

<style>
.itemList{
    display: flex;justify-content: space-between;
    align-items: center;
    height: 35px;
}
.itemList li{
    margin-bottom: 5px;
}
.list{
    display: flex;
    gap:10px;
}
.del{
    background: skyblue;
    padding: 0 20px;
    cursor: pointer;
    align-self: start;
    height: 100%;
    justify-content: center;
    align-items: center;
    display: flex;
}

</style>