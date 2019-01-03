<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
        <li class="item" v-for="item of recommendList" :key="item.id">
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
    data () {
        return {
               recommendList: [{
                     id: '0001',
                     imgUrl: 'http://img1.qunarzz.com/sight/p0/1508/2e/d9363ce50a88c8c5ff5a138c67687cd4.water.jpg_200x200_1c15c8f5.jpg',
                     title: '深圳野生动物园',
                     desc: '浪漫深圳首站,野生主题乐园',
                 },{
                     id: '0002',
                     imgUrl: 'http://img1.qunarzz.com/sight/p0/1502/15/15ca1d0eab6bf46c.water.jpg_200x200_50ca7bb1.jpg',
                     title: '深圳野生动物园',
                     desc: '浪漫深圳首站,野生主题乐园',
                 },{
                     id: '0003',
                     imgUrl: 'http://img1.qunarzz.com/sight/p0/1812/a7/a7783a2362ed222ba3.water.jpg_200x200_9411c96d.jpg',
                     title: '深圳野生动物园',
                     desc: '浪漫深圳首站,野生主题乐园',
                 },{
                     id: '0004',
                     imgUrl: 'http://img1.qunarzz.com/sight/p0/1507/64/34362835b4a219af8b36803d31a6380f.water.jpg_200x200_bc5c0452.jpg',
                     title: '深圳野生动物园',
                     desc: '浪漫深圳首站,野生主题乐园',
                 }]
                }
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
