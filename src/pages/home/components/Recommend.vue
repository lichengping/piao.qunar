<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
        <li class="item" v-for="item of list" :key="item.id">
            <img class="item-img" :src="item.imgUlr" alt=""> 
            <div class="item-info">
                <p class="item-title">{{item.title}}</p>
                <p class="item-desc">{{item.desc}}</p>
                <button class="item-button">查看详情</button>
            </div>
        </li>
    </ul>
  </div>
</template>
<script>
export default {
    name: 'HomeRecommend',
    //接收父组件传的值
    props: {
        list: Array
    }
}
</script>
<style scoped>
   .title { 
       line-height: 0.8rem;
       background: #eee;
       text-indent: 0.2rem;
   }
   .item {
       overflow: hidden;
       display: flex;
       height: 1.9rem;
   }
   .item .item-img {
       width: 1.7rem;
       height: 1.7rem;
       padding: .1rem;
   }
   .item .item-info {
       flex: 1;
       padding: .1rem; 
       line-height: 0.5rem;
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
   .item-button {
       background: #ff8300;
       padding: .1rem;
       border-radius: .06rem; 
       padding: 0 .2rem;
       color: #fff;
       margin-top: .2rem; 
   }
</style>
