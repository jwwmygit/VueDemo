<template>
  <div>
    <img src="./assets/logo.png" alt="" class="logo">
  <HelloWord/>
  </div>
</template>
<script>
  import HelloWord from './components/HelloWorld.vue'
  export default {
       components:{
         HelloWord
       }
  }
</script>
<style>
  .logo{
    width: 200px;
    height: 200px;

  }
</style>

