<template>
  <div class="modal">
    <!-- <h3>
        <slot name="header"></slot>

    </h3> -->
    <p>
        <slot name="body"></slot>
    </p>
    <div class="close">
        <img src="../assets/cancel.png" alt="">
    </div>
    <div class="alert">
        <img src="../assets/schedule.png" alt="">
        ToDoList
    </div>
  </div>
  
</template>

<script>
export default {

}
</script>

<style lang="scss">
    .modal{
        width: 250px;
        height: 100px;
        background: rgb(235, 225, 211);
        position: fixed;
        left: 50%;
        top: 10%;
        transform: translateX(-50%);
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        gap:5px;
        border-radius: 20px;
        box-shadow: 0 0 10px rgba(0,0,0,0.3);
        p{
            margin-top: 20px;
            font-size: 17px;
            font-weight: 500;
        }
        &::before{
            content: "";display: block;
            width: 250px;height: 30px;
            background: rgb(211, 167, 107); 
            border-radius: 20px 20px 0 0 ;
            position: absolute;
            top: 0;
        }
        .close{
            position: absolute;
            right: 8px;top: 5px;
            cursor: pointer;
            img{
                width: 20px;height: 20px;
            }
        }
        .alert{
            position: absolute;
            left: 12px;top:3px;
            display: flex;
            align-items: center;
            color:rgb(93, 50, 8);
            font-weight: bold;
            font-size: 17px;
            img{
                width: 18px;height: 18px;
                margin-right: 10px;
                }
        }
        
    }
</style>