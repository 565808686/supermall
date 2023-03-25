<template>
  <div class="recommend-view">
    <div v-for="(item,index) in recommends" :key="index">
    <a :href="item.link">
      <img :src="item.image" alt="">
      <div>{{item.title}}</div>
    </a>
   </div>
  </div>
</template>
<script>
export default {
  name:'RecommendView',
  props:{
    recommends:{
      type:Array,
      dafault(){
        return []
      }
    }
  }
}
</script>
<style scoped>
 .recommend-view{
  display: flex;
  width: 100%;
  justify-content: space-around;
  text-align: center;
  margin-top: 12px;
 }
 .recommend-view img{
  width: 65px;
  height: 65px;
  margin-top: 2px;
 }
</style>