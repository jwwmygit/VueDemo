<template>
  <div>
    <header class="site-header jumbotron">
      <div class="container">
        <div class="row">
          <div class="col-xs-12">
            <h1>请发表对React的评论</h1>
          </div>
        </div>
      </div>
    </header>
    <div class="container">
      <Add  :addComents="addComents"/>
      <List :comments="comments" :deleteComents="deleteComents"/>
    </div>
  </div>
</template>
<script>
  import Add from './components/Add.vue'
  import List from './components/List.vue'
  export default {
    components:{
      Add,
      List
    },
    data(){
     return {
       comments:[
         {name:'张三', content:"Vue"}
       ]

     }
    },
    methods:{
      addComents(comment){
       this.comments.unshift(comment)
      },
      deleteComents(index){
        this.comments.splice(index,1)
      }
    }

  }

</script>
<style>

</style>
