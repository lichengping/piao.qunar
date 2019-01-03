<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
        <li class="item" v-for="item of WeekendList" :key="item.id">
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
    data () {
        return {
               WeekendList: [{
                     id: '0001',
                     imgUrl: 'http://img1.qunarzz.com/sight/source/1602/88/bf120edeaea383.jpg_r_640x214_f8591f7b.jpg',
                     title: '欢乐长隆',
                     desc: '世界欢乐汇聚长隆，这里拥有多个大型游乐设备和精彩的演出，和小伙伴们一起感受刺激的体验',
                 },{
                     id: '0002',
                     imgUrl: 'http://img1.qunarzz.com/sight/source/1811/15/66f14e0fd6fbb.jpg_r_640x214_5d69f21d.jpg',
                     title: '南国冰雪乐园',
                     desc: '这里可以让你在南国感受到北国风光，让南国的你“零距离”感受北国银装素裹壮观之景',
                 },{
                     id: '0003',
                     imgUrl: 'http://img1.qunarzz.com/sight/source/1505/b9/f9d8ace21c06.jpg_r_640x214_1f239a81.jpg',
                     title: '深圳必打卡',
                     desc: '来到深圳，你需要来这里签到',
                 },{
                     id: '0004',
                     imgUrl: 'http://img1.qunarzz.com/sight/source/1505/fa/ca65fde9677de2.jpg_r_640x214_4500e3ff.jpg',
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
