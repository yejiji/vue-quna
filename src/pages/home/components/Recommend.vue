<template>
   <div class="recommend">
       <div class="recommend-title">
           <img class="recommed-title-img" src="http://img1.qunarzz.com/piao/fusion/1711/16/bfbb9874e8f11402.png">
           <span class="recommed-title-desc">本周热门榜单</span>
           <a class="recommed-title-a">全部榜单</a>
       </div>
       <ul>
       
           <router-link 
           tag="li"
           class="item border-bottom" 
           v-for="item of list" 
           :key="item.id"
           :to="'/detail/'+item.id">
               <img class="item-img" :src="item.imgUrl">    
               <div class="item-info">
                   <p class="item-title">{{item.title}}</p>
                   <p class="item-desc">{{item.desc}}</p>
               </div>
               <button class="item-button" >查看详情</button>
           </router-link>
       
       </ul>
   </div>
 
</template>

<script>

export default {
    name:'HomeRecommend',
   props: {
     list:Array
   }
    
}
</script>
<style lang="stylus" scoped>
@import '~styles/mixins.styl'  
.recommend
  margin-top:.2rem 
  background #fff
  .recommend-title
    position: relative
    line-height .4rem
    padding: .24rem 0 .26rem
    .recommed-title-img
      display: inline-block
      overflow: hidden
      width: .3rem
      height: .3rem
      margin-left: .2rem
      vertical-align: top
    .recommed-title-desc
      display: inline-block
      margin-left: .08rem
      height: .44rem
      color: #212121
      font-size: .32rem
      line-height: .44rem
    .recommed-title-a
      position: absolute
      top: .36rem
      right: .32rem
      color: #616161
      font-size: .24rem
      line-height: .28rem 
  .item
    position relative
    overflow hidden
    display flex
    width  100%
    padding: .2rem 0
    height 100%
    .item-img
      float left
      width: 1.7rem
      height: 1.7rem
      padding: .1rem
    .item-info
      flex 1
      overflow: hidden
      padding-left: .22rem
      min-width 0
      .item-title
        margin-top: .26rem
        height: .44rem
        color: #212121
        font-size: .32rem
        line-height: .44rem
        ellipsis()
      .item-desc
        display: inline-block
        margin-top: .40rem
        margin-right: .24rem
        background: #fff9f9
        padding: .04rem .1rem
        color: #f55
        font-size: .24rem
        line-height: .34rem
        ellipsis()
    .item-button
      position absolute
      right: 0.2rem
      bottom: 0.1rem
      height: 0.4rem
      width: 1rem
      background: #fdb842
      color: #fff
      font-size: 0.2rem


</style>
