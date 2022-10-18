<template>
  <ul>
    <li v-for="(item,i) in todoItem" :key="item">{{item}}</li>
    
  </ul>
</template>

<script>
export default {
    props : [
        "todoItem"
    ]
}
</script>

<style>

</style>