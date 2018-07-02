<template>
    <div class="todo-container">
      <div class="todo-wrap">
<!--映射-->
        <todo-header :addTodo="addTodo"/>
        <List :todos="todos" :deleteB="deleteB"/>
        <todo-footer :deleteComplete="deleteComplete" :todos="todos" :selectAll="selectAll" />
      </div>
    </div>
</template>
<script>
import Header from './components/Header.vue';
import List from './components/List.vue';
import Footer from './components/Footer.vue';
  export default {//配置对象
        data() {
          return {
            todos: [
              {title: '吃饭', completed: false},
              {title: '睡觉', completed: false},
              {title: '打豆豆', completed: true}
            ]
          }
        },
        components: {
          TodoHeader:Header,
          List,
          TodoFooter: Footer
        },
    methods:{
//          输入数据添加到列表里,这个方法要给hander用
          addTodo(todo){
            this.todos.unshift(todo)
          },
//      点击按钮删除列表中的每一项
        deleteB(index){
            this.todos.splice(index,1)
        },
      deleteComplete(){
       this.todos= this.todos.filter(todo=>!todo.completed)
      },
      selectAll(check){
       this.todos.forEach((todo)=>todo.completed=check)
      }
    }
  }
</script>
<style scoped>
  .todo-container {
    width: 600px;
    margin: 0 auto;
  }
  .todo-container .todo-wrap {
    padding: 10px;
    border: 1px solid #ddd;
    border-radius: 5px;
  }
</style>

