<template>
  <div>
    <my-header></my-header>
    <div id="content">
      <slideShow></slideShow>
      <solution></solution>
    </div>
    <my-footer></my-footer>
  </div>
</template>
<script>
  import myHeader from "./components/header"
  import myFooter from "./components/footer"
  import slideShow from "./components/slideShow"
  import solution from "./components/solution"
  export default{
    components:{
      myHeader,
      myFooter,
      slideShow,
      solution
    }
  }
</script>
<style>
  *{
    margin: 0;
    padding: 0;
  }
  body{
    min-width: 1900px;
  }
  #content{
    width: 100%;
  }
</style>