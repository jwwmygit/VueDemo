<template>
  <ul class="todo-main">
    <!--遍历todos-->
   <Item v-for="(todo,index) in todos" :key="index" :todo="todo"
         :index="index" :deleteB="deleteB"
   />
  </ul>
</template>
<script>
  import Item from './item.vue'
    export default {
//    声明式接收属性
      props:['todos','deleteB'],
      components:{
        Item
      }
    }

</script>
<style scoped>
  .todo-main {
    margin-left: 0px;
    border: 1px solid #ddd;
    border-radius: 2px;
    padding: 0px;
  }

  .todo-empty {
    height: 40px;
    line-height: 40px;
    border: 1px solid #ddd;
    border-radius: 2px;
    padding-left: 5px;
    margin-top: 10px;
  }


</style>
