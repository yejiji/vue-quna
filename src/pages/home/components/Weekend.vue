<template>
      <div class="weekend">
       <div class="weekend-title">
           周末去哪儿
       </div>
       <ul>
           <li class="item border-bottom" v-for="item of list" :key="item.id">
               <div class="item-img">
                    <img  :src="item.imgUrl">  
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
    name:'HomeWeekend',
    props: {
        list:Array
    }
   
}
</script>
<style lang="stylus" scoped>
@import '~styles/mixins.styl'  
.weekend
  .weekend-title
    height: .8rem
    padding-left: .26rem
    line-height: .8rem
    color: #212121
  .item
    display: block
    width: 100%
    height: 100%
    .item-img
      overflow: hidden
      height: 0
      padding-bottom: 37.4375%
    .item-info
      position: relative
      padding: .14rem .2rem .2rem .2rem
      .item-title
        padding-right: 1.4rem
        color: #212121
        font-size: .28rem
        line-height: .48rem
        ellipsis()
      .item-desc
        padding-right: 1.4rem
        color: #616161
        font-size: .24rem
        line-height: .42rem
        ellipsis()



</style>

