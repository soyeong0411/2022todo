<template>
      <div class="listWrap">
          <ul>
            <li v-for="(item,i) in todoItem" :key="i" class="itemList">
                <div class="list">
                    <img src="../assets/pin.png" alt="">{{item}}
                </div>
                <div class="del" @click="removeDel(i,item)" >  <!-- array, local 에서 삭제 -->
                    <img src="../assets/del.png" alt="">
                </div>
            </li>
          </ul>
      </div>
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

<style lang="scss">
.listWrap{
    width: 340px;
    min-height: 200px;
    background: rgb(235, 225, 211);
    border-radius: 10px;margin-top: 20px;
    .itemList{
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 35px;
    margin: 7px 0;
    border-bottom: 1px dashed rgb(93, 50, 8);
    padding: 0 7px;
    .list{
        display: flex;
        align-items: center;
        gap:10px;
        img{
        width: 20px;height: 20px;
        }
    }
    .del{
    // padding: 0 20px;
    cursor: pointer;
    justify-content:right;
    align-items: center;
    display: flex;
    // align-self: start;
    // height: 100%;
    img{
        width: 25px;height: 24px;
    }
    }
}
}

    




</style>