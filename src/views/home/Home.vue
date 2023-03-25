<template>
  <div id="home">
    <nav-bar class="home-nav">
      <div slot="left"><img src="assets/img/" alt=""></div>
      <span slot="center">购物车</span>
    </nav-bar>
    <!-- 轮播图  抽离出去 -->
    <!-- <swiper>
      <swiper-item v-for="(item,index) in banners" :key="index">
        <a :href="item.link">
          <img :src="item.image" alt="">
        </a>
      </swiper-item>
    </swiper> -->
    <home-swiper :banners="banners"></home-swiper>

     <!-- 推荐页展示  抽离出去 -->
   <!-- <div v-for="(item,index) in recommends" :key="index">
    <a :href="item.link">
      <img :src="item.image" alt="">
      <div>{{item.title}}</div>
    </a>
   </div> -->
   <recommend-view :recommends="recommends"></recommend-view>
  </div>
</template>

<script>
import NavBar from 'components/common/navbar/NavBar'
import {getHomeMultidata} from 'network/home.js'
import {Swiper, SwiperItem} from 'components/common/swiper/index'
import HomeSwiper from './childComps/HomeSwiper.vue'
import RecommendView from './childComps/RecommendView.vue'
// import Swiper from '../../components/common/swiper/Swiper.vue'
// import SwiperItem from '../../components/common/swiper/SwiperItem.vue'
  export default {
    name: "Home",
    data(){
      return {
      banners:[],
      recommends:[]
      }
    },
    components:{
      NavBar,
      HomeSwiper,
      RecommendView
      //  Swiper, 
      //  SwiperItem
       
    },
    created(){
      getHomeMultidata().then(res=>{
        console.log(res);
        this.banners=res.data.banner.list
        this.recommends=res.data.recommend.list
      })
    }
  }
</script>

<style>
.home-nav{
  background-color: pink;
  color: aliceblue;
}
</style>
