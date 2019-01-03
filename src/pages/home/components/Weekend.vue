<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
        <li class="item" v-for="item of list" :key="item.id">
            <div class="item-img-wrapper">
               <img class="item-img" :src="item.imgUlr" alt=""> 
            </div>
            <div class="item-info">
                <p class="item-title">{{item.title}}</p>
                <p class="item-desc">{{item.desc}}</p>
            </div>
        </li>
    </ul>
  </div>
</template>
<script>
export default {
    name: 'HomeWeekend',
   // 子组件接收父组件的值
   props :{
       list:Array
   }
}
</script>
<style scoped>
   .title { 
       line-height: 0.8rem;
       background: #eee;
       text-indent: 0.2rem;
   }
   .item-img-wrapper {
       overflow: hidden;
       height: 0;
       padding-bottom: 33.4%;
   }
   .item .item-img {
       width: 100%;
   }
   .item-info {
       padding: .1rem;
   }
   .itme-title {
       line-height: .54rem;
       font-size: .32rem;
       color: #000;
   }
   .itme-desc {
       line-height: .4rem;
       color: #ccc;
   }
</style>
