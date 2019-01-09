<template>
   <ul class="list">
       <li class="item" 
       v-for="item of letters" :key="item"
       @touchstart = "handleTouchStart"
       @touchmove = " handleTouchMove"
       @touchend = "handleTouchEnd "
       @click = "handleLetterClick"
       :ref = 'item'
       >
       {{item}}
       </li>
   </ul>
</template>

<script>

export default {
    name: 'CityAlphabet',
    //接收父组件传来的值
    props:{
        cities:Object
    },
    //计算属性 将cities转变为新的数据为数组,通数组下标判断当前滑动的字母位置
    computed: {
        letters () {
            const letters = [];
            for(let i in this.cities){
                letters.push(i);
            }
            return letters
        }
    },
    data () {
         return {
             touchStarts: false
         }
    },
    methods: {
        //点击跳转指定
        handleLetterClick (e) {
           //子组件向父组件传值  $emit('向外触发事件',发出去的数据)
           this.$emit('change',e.target.innerText)            
        },
        //手指触摸
        handleTouchStart () {
            this.touchStarts = true;
        },
        handleTouchMove (e) {
            //当在滑动
            if(this.touchStarts) {
               //当前字母在的位置
               const startY = this.$refs['A'][0].offsetTop
               //当前滑动的位置到订部的header头部的位置
               //首页要剪切header头部的位置高度
               const touchY = e.touches[0].clientY - 79
               //index是当前滑动距离到第一字母A的距离
               const index = Math.floor((touchY - startY) / 20)
               console.log(index);
               if(index >= 0 && index < this.letters.length) {
                   this.$emit('change',this.letters[index])
               }
            }
        },
        //结束滑动时
        handleTouchEnd () {
            this.touchStarts = false;
        },
    }

}
</script>

<style scoped>
  .list {
      display: flex;
      flex-direction: column;
      justify-content: center;
      position: absolute;
      top: 1.58rem;
      right: 0;
      bottom: 0;
      width: .4rem;
  }
  .list .item {
      text-align: center;
      line-height: .4rem;
      color: #00bcd4;
  }
</style>