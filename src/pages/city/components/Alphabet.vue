<template>
   <ul class="list">
       <li class="item"  v-for="(item, key) of cities" :key="key">{{key}}</li>
   </ul>
</template>

<script>

export default {
    name: 'CityAlphabet',
    //接收父组件传来的值
    props:{
        cities:Object
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