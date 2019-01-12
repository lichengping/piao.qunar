<template>
<div>
  <home-header :city="city"></home-header>
  <home-swiper :list="swiperList"></home-swiper>
  <home-icons :icon="iconList"></home-icons>
  <home-recommend :list="recommendList"></home-recommend>
  <home-weekend :list="weekendList"></home-weekend>
</div>
</template>

<script>
//引入better-scroll包
import BScroll from 'better-scroll'

import HomeHeader from './components/header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeRecommend from './components/Recommend'
import HomeWeekend from './components/Weekend'
import axios from 'axios'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  },
  data () {
     return {
       //父组件向子组件传值  "通过属性" 头部导航数据
       city: '',
       //父组件向子组件传值  "通过属性" 轮播数据
       swiperList: [],
       //父组件向子组件传值  "通过属性" 分类栏  
       iconList: [],
       //父组件向子组件传值  "通过属性" 周末去哪
       recommendList: [],
       //父组件向子组件传值  "通过属性" 
       weekendList: []
     }
  },
  methods: {
    getHomeInfo () {
       //请求ajax数据
      axios.get('/static/mock/index.json')
        //返回值
        .then(this.getHomeInfoSucc)
    },
    //方法  获取数据
    getHomeInfoSucc (res) {
      //获取数据内容
      res = res.data;
      //ret指后端返回的一个数据项, true或false  是否成功
      if (res.ret && res.data) {
         const data = res.data
         this.city = data.city
         this.swiperList = data.swiperList;
         this.iconList = data.iconList;
         this.recommendList = data.recommendList;
         this.weekendList = data.weekendList;
      }
      console.log(res);
    }
  },
  mounted () {
    this.getHomeInfo();
  }
}
</script>
<style>
  .list {
    overflow: hidden;
  }
</style>
