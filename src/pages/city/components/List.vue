<template>
   <!-- ref获取dom -->
  <div class="list" ref="wrapper">
      <!-- 第三方插件better-scroll -->
    <div>  
     <div class="area">
         <div class="title border-bottom">当前城市</div>
         <div class="button-list">
             <div class="button-wrapper">
                 <div class="button">深圳</div>
             </div>
         </div>
     </div>
     <div class="area">
         <div class="title border-bottom">热门城市</div>
         <div class="button-list">
             <div class="button-wrapper" v-for="item of hot" :key="item.id">
                 <div class="button">{{item.name}}</div>
             </div>
         </div>
     </div>
     <div class="area" v-for="(item, key) of cities" :key="key">
         <div class="title border-bottom">{{key}}</div>
         <div class="item-list">
             <div class="item" v-for="innerItem of item" :key="innerItem.id">{{innerItem.name}}</div>
         </div>
     </div>
    </div> 
  </div>
</template>

<script>
//引入better-scroll包
import BScroll from 'better-scroll'
export default {
    name: 'CityList',
    //接收父组件传来的值
    props: {
      hot: Array,
      cities: Object,
    },
    // 生命周期函数mounted:在页面dom挂载完毕之后执行
    mounted () {
        this.scroll = new BScroll(this.$refs.wrapper)
    }
}
</script>

<style scoped>
  /* 边框 */
  .border-bottom {
       border-bottom: 1px solid #ccc;
  }
  .list {
      overflow: hidden;
      position: absolute;
      top:1.56rem;
      left: 0;
      right: 0;
      bottom: 0;
  }
  /* 列表样式 */
  .list .title {
      line-height: .56rem;
      background: #eee;
      padding-left: .2rem;
      color: #666;
      font-size: .26rem;
  }
  .button-list {
      display: flex;
      flex-wrap: wrap;
      padding-right: .6rem;
  }
  .button-list .button-wrapper {
       width: 33.33%;
       text-align: center;
  }
  .button-list .button {
     margin: .1rem;
     padding: .1rem 0;
     border: 0.02rem solid #ccc;
     border-radius: .08rem;
  }
  .item-list .item {
      line-height: .54rem;
      color: #666;
      padding-left: .2rem; 
      border-bottom:  0.02rem solid #ccc;
  }
</style>