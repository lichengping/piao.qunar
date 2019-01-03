<template>
  <div class="wrapper">
     <swiper :options="swiperOption" v-if="showSwiper">
      <swiper-slide v-for="item of list" :key="item.id">
          <img class="swiper-img"  :src="item.imgUrl" alt="">
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
    name: 'HomeSwiper',
    //子组件接收父组件的值
    props: {
      //接收数据类型  Array
      list: Array
    },
    data () {
      return {
         swiperOption: {
        // some swiper options/callbacks
        pagination: ".swiper-pagination",
        loop: true
       },
    }
  },
  //计算属性
  computed: {
    showSwiper () {
      //判断传的数组是否为空
      return this.list.length
    }
  }
}
</script>
<style scoped>
  .wrapper >>> .swiper-pagination-bullet {
      background: #fff;
  }
  .wrapper {
    overflow: hidden;
    width: 100%;
    height: 0;
    padding-bottom: 31.25%;
  }
  .swiper-img{
    width: 100%;
  } 
</style>