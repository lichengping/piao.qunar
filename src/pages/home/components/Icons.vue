<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon"  v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img
              class="icon-img-content"
              :src='item.imgUrl'
              alt
            />
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: "HomeIcons",
    //接收父组件传来的值
    props: {
         icon:Array
    }, 
    //设置默认不自动滚动
    data () {
        return {
           swiperOption: {
               autoplay: false
           } 
        }
    }, 
    computed: {
        pages() {
            const pages = [];
            this.icon.forEach((item,index) => {
                const page = Math.floor(index / 8)
                if(!pages[page]) {
                    pages[page] = []
                }
                pages[page].push(item)
            })
            return pages
        }
    }
}
</script>
<style scoped>
.icons >>> .swiper-container {
  height: 0;
  padding-bottom: 50%;
  overflow: hidden;
}
.icons .icon {
  position: relative;
  width: 25%;
  padding-bottom: 25%;
  float: left;
}
.icons .icon .icon-img {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0.44rem;
  box-sizing: border-box;
}
.icon-img-content {
  display: block;
  margin: 0 auto;
  height: 100%;
}
.icon-desc {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  height: 0.44rem;
  line-height: 0.44rem;
  text-align: center;
}
</style>
