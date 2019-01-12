<template>
 <div>
  <div class="search">
    <input class="search-input" v-model="keyword" type="text" placeholder="输入城市名或拼音">
  </div>
  <div class="search-content" ref="search" v-show="keyword">
     <ul>
       <li class="search-item" v-for="item of list" :key="item.index">{{item.name}}</li>
       <li class="search0item" v-show="hasNoData">没有匹配到结果</li>
     </ul>
  </div>
  </div>
</template>

<script>
//引入better-scroll包
import BScroll from 'better-scroll'
export default {
    name: 'CitySearch',
    props: {
      cities: Object  
    },
    data() {
      return {
        keyword: '',
        //存储用户搜索信息
        list: [],
        //用于节流函数 提交代码效应
        timer: null,
      }
    }, 
    //计算属性  将逻辑cong标签提出来
    computed: {
      
      hasNoData() {
        return !this.list.length
      }
    },
    //侦听器
    watch: {
      keyword () {
        if(this.timer) {
          clearTimeout(this.timer)
        }
        //检测搜索框是否为空
        if(!this.keyword){
          this.list = []
          return
        }
        this.timer = setTimeout(() => {
           const result = []
           //循环字母
           for (let i in this.cities) {
             //遍历每个字母中的城市(ABC...)
              this.cities[i].forEach((value) => {
                  if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1){
                      result.push(value);
                  }
              });
           }   
           //将搜索内容正确的城市添加到list中
           this.list = result 
        }, 100)
      }
    },
    //生命周期函数
    mounted () {
      this.scroll = new BScroll(this.$refs.search)
    }
}
</script>

<style scoped>
   .search {
     height: .72rem;
     padding: 0 .1rem;
     background: #00bcd4;
   }
   .search-input {
     box-sizing: border-box;
     height: .62rem;
     width: 100%;
     line-height: .62rem;
     border-radius: 0.08rem;
     padding: 0 .1rem; 
     color: #666;
   }
   .search-content {
     z-index: 1;
     overflow: hidden;
     position: absolute;
     top: 1.58rem;
     left: 0;
     right: 0;
     bottom: 0;
     background: #666;
   }
   .search-item {
     line-height: .62rem;
     padding-left: .2rem;
     background: #fff;
     color: #666;
     border-bottom: 1px solid #ccc;
   }
</style>