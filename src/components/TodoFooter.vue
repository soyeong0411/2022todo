<template>
  <div class="clearWrap">
    <div class="clearAll" @click="$emit('clearAll')">
      <img src="../assets/household-chores.png" alt=""> 전체삭제
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss">
.clearWrap{
  display: flex;
  justify-content: end;
  margin-top: 20px;
  cursor: pointer;
  .clearAll{
    display: flex;
    justify-content: center;
    align-items: center;
    background: rgb(176, 129, 82);
    color:rgb(235, 225, 211);
    height: 35px;width: 120px;
    border-radius: 10px;
    font-size: 15px;
    img{
      width: 22px;height: 22px;
      margin-right: 5px;
    }
  }
}

</style>