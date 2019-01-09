<template>
<div>
  <city-header></city-header>
  <city-search></city-search>
  <city-list :cities="cities" :hot="hotCities"></city-list>
  <city-alphabet :cities="cities"></city-alphabet>
</div>
</template>

<script>
import axios from 'axios'
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
import { log } from 'util';
export default {
    name: 'City',
    components: {
      CityHeader,
      CitySearch,
      CityList,
      CityAlphabet,
    },
    data() {
      return {
        // 城市名字  父组件向子组件传值
        cities:{},
        //热门地名   父组件向子组件传值
        hotCities:[]
      }
    },
    methods: {
      getCityInfo () {
        //发ajax请求
        axios.get('static/mock/city.json')
        //返回值
        .then(this.handleGetCityInfoSucc)
      },
      //方法 接收后台模拟数据
      handleGetCityInfoSucc(res) {
        //获取数据内容
        res = res.data;
        //ret指后端返回的一个数据项, true或false  是否成功
        if(res.ret && res.data){
           const data = res.data;
           this.cities = data.cities;
           this.hotCities = data.hotCities;
        }
          console.log(res);
          
      }
    },
    // 生命周期函数mounted:在页面dom挂载完毕之后执行
    mounted () {
        this.getCityInfo()
    }
}
</script>

<style scoped>
  
</style>
