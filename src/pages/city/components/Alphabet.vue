<template>
    <ul class="list">
       <li 
       class="item" v-for="item of letters" :key="item"
       @click="handleLetterClick"
       @touchstart.prevent="handleTouchStart"
       @touchmove="handleTouchMove"
       @touchend="handleTouchEnd"
       >
         {{item}}
       </li>
 
    </ul>
</template>
<script>
export default {
    name: 'CityAlphabet',
    props : {
        cities : Object
    },
    computed: {
        letters() {
            const letters = []
            for(let i in this.cities){
                console.log(i)
                letters.push(i)
            }
            return letters
        } 
    },
    data() {
        return {
            touchStatus : false
        }
    },
    methods: {
        handleLetterClick (e) {
            this.$emit('change',e.target.innerText)
            
        },
        handleTouchStart () {
            this.touchStatus = true 
        },
        handleTouchMove () {
            if(this.touchStatus) {

            } 
        },
        handleTouchEnd () {
            this.touchStatus = false 
        }
    }
}
</script>
<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .list
    display flex
    flex-direction: column
    justify-content: center  
    position absolute
    top:1.78rem
    right 0
    bottom 0
    width 0.4rem 

    .item
      line-height .4rem
      text-align  center
      color   #05a6d2ab   
</style>
