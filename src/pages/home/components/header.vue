<template>
<div class="header">
  <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
  </div>
  <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      输入城市景点游玩主题
</div>
   <!-- vue内置跳转组件 -->
  <router-link to='/city'>
  <div class="header-right">
      {{this.city}}
      <span class="iconfont">&#xe64a;</span>
  </div>
  </router-link>
</div>
</template>

<script>
export default {
  name: 'HomeHeader',
    //子组件接收父组件传来的值  方法
  props: {
    //city类型必须是string类型  注意大写String
    city: String
  }
}
</script>
<style scoped>
  .header{
    display: flex;
    background: #00bcd4;
    line-height: 0.86rem;
    color: #fff;
  }
  .header .header-left{
    width: 0.64rem;
  }
  .header-left .back-icon{
      text-align: center;
      font-size: 0.4rem;
  }
  .header .header-right{
    width: 1.24rem;
    color: #fff;
  }
  .header .header-input{
    flex: 1;
    background: #fff;
    border-radius: .1rem;
    height: 0.64rem;
    line-height: 0.64rem;
    margin-top:.11rem;
    margin-left:0.1rem; 
    padding-left: 0.1rem;
    color: #ccc; 
  }
</style>
