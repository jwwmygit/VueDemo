<template>
  <li :style="{background: bgColor}" @mouseenter="handleEnter(true)" @mouseleave="handleEnter(false)">
    <label>
      <input type="checkbox" v-model="todo.completed"/>
      <span>{{todo.title}}</span>
    </label>
    <button class="btn btn-danger"  v-show="isShow" @click="deleteB(index)">删除</button>
  </li>

</template>
<script>

    export default {
    //接收声明属性
      data(){
        return {
          bgColor:'#fff',
          isShow:false
        }
      },
      props:{
        todo:Object,//声明属性和属性值的类型
        index:Number,
        deleteB:Function
      },
      methods:{
        handleEnter(isEnter){
          if(isEnter){
            this.bgColor='gray';
            this.isShow=true
          }else {
            this.bgColor='#fff';
            this.isShow=false
          }
        }
      }
    }


</script>
<style>
  li {
    list-style: none;
    height: 36px;
    line-height: 36px;
    padding: 0 5px;
    border-bottom: 1px solid #ddd;
  }

  li label {
    float: left;
    cursor: pointer;
  }

  li label li input {
    vertical-align: middle;
    margin-right: 6px;
    position: relative;
    top: -1px;
  }

  li button {
    float: right;
    display: none;
    margin-top: 3px;
  }

  li:before {
    content: initial;
  }

  li:last-child {
    border-bottom: none;
  }



</style>
