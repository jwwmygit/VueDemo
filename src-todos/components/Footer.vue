<template>
  <div class="todo-footer">
    <label>
      <input type="checkbox" v-model="isCheck"/>
    </label>
    <span>
          <span>已完成{{competedCount}}</span> / 全部{{todos.length}}
        </span>
    <button class="btn btn-danger" v-show="competedCount" @click="deleteComplete">清除已完成任务</button>
  </div>
</template>
<script>

    export default {
//      声明式接收属性
      props:{
        todos:Array,
        deleteComplete:Function,
        selectAll:Function
      },
      computed:{
        competedCount(){
          return this.todos.reduce((pro,todo)=>pro+(todo.completed?1:0),0)
        },
        isCheck:{
          get(){
            return this.todos.length===this.competedCount;
          },
          set(value){
            this.selectAll(value)
          }

        }

      }
    }

</script >
<style scoped>


  .todo-footer {
    height: 40px;
    line-height: 40px;
    padding-left: 6px;
    margin-top: 5px;
  }

  .todo-footer label {
    display: inline-block;
    margin-right: 20px;
    cursor: pointer;
  }

  .todo-footer label input {
    position: relative;
    top: -1px;
    vertical-align: middle;
    margin-right: 5px;
  }

  .todo-footer button {
    float: right;
    margin-top: 5px;
  }

</style>
