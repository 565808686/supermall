<template>
  <div class="nav-bar">
    <div id="left"><slot name='left'></slot></div>
    <div id="center"><slot name='center'></slot></div>
    <div id="right"><slot name='right'></slot></div>
  </div>
</template>

<script>
  export default {
    name: "NavBar"
  }
</script>

<style scoped>
  .nav-bar {
    display: flex;
    height:44px;
    line-height: 44px;
    
  
    

    box-shadow: 0 -1px 1px rgba(100,100,100,.2);
  }
  #right, #left{
    width:60px;
    
  }
  #center{
    flex:1;
    text-align: center;
    /* background-color: black; */
  }
</style>
