<template>
<div class="header">
  <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
  </div>
  <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      输入城市景点游玩主题
</div>
  <div class="header-right">
      城市
      <span class="iconfont">&#xe64a;</span>
  </div>
</div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>
<style scoped>
  .header{
    display: flex;
    background: #00bcd4;
    line-height: 0.86rem;
    /* text-align: center; */
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
