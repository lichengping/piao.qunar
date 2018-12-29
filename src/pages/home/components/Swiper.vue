<template>
  <div class="wrapper">
     <swiper :options="swiperOption">
      <swiper-slide v-for="item of swiperList" :key="item.id">
          <img class="swiper-img"  :src="item.imgUrl" alt="">
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
    name: 'HomeSwiper',
    data () {
      return {
        swiperOption: {
          pagination: '.swiper-pagination',
          loop: true,
        },
        swiperList: [{
            id: '0001',
            imgUrl: 'http://img1.qunarzz.com/piao/fusion/1811/f7/72ce947f4dff4c02.jpg_750x200_aa583dba.jpg'
        }, {
            id: '0002',
            imgUrl: 'http://img1.qunarzz.com/piao/fusion/1812/48/5713e2a2ba72f902.jpg_750x200_2b382dac.jpg'
        }, {
            id: '0003',
            imgUrl: 'http://img1.qunarzz.com/piao/fusion/1811/39/6b1f0402bb1d5902.jpg_750x200_3c7661d6.jpg'
        }]
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